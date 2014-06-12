-------------------------------
Omeka_View_Helper_SearchFilters
-------------------------------

.. php:class:: Omeka_View_Helper_SearchFilters

extends :php:class:`Omeka_View_Helper_AbstractSearch`

    Return a list of search filters in the current request.

    .. php:method:: searchFilters($options = array())

        Return a list of current search filters in use.

        :type $options: array
        :param $options: Valid options are as follows: - id (string): the ID of the filter wrapping div.
        :returns: string
