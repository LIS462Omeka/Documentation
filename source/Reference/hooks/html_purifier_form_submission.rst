#############################
html_purifier_form_submission
#############################


*****
Usage
*****

Use this hook to run HTMLPurifier on submitted text. After purifying, reset the post data on the request object.

*********
Arguments
*********

``HTMLPurifier`` purifier
    The HTMLPurifier object 


********
Examples
********

.. code-block:: php

    class SimplePagesPlugin extends Omeka_Plugin_AbstractPlugin
    {
    
        protected $_hooks = array('html_purifier_form_submission');
    
        /**
         * Filter the 'text' field of the simple-pages form, but only if the 
         * 'simple_pages_filter_page' setting has been enabled from within the
         * configuration form.
         * 
         * @param array $args Hook args, contains:
         *  'request': Zend_Controller_Request_Http
         *  'purifier': HTMLPurifier
         */
        function hookHtmlPurifierFormSubmission($args)
        {
            $request = Zend_Controller_Front::getInstance()->getRequest();
            $purifier = $args['purifier'];
    
            // If we aren't editing or adding a page in SimplePages, don't do anything.
            if ($request->getModuleName() != 'simple-pages' or !in_array($request->getActionName(), array('edit', 'add'))) {
                return;
            }
            
            // Do not filter HTML for the request unless this configuration directive is on.
            if (!get_option('simple_pages_filter_page')) {
                return;
            }
            
            $post = $request->getPost();
            $post['text'] = $purifier->purify($post['text']); 
            $request->setPost($post);
        }    
    }
