.. _searchsql:


##########
search_sql
##########

*****
Usage
*****

Modifies the SQL query used.

This hook can be used when a custom search strategy is added using the :ref:`search_query_types` filter.


*********
Arguments
*********

:php:class:`Omeka_Db_Select` select
    The select object to modify

``array`` params
    Array of parameters to modify the search.

********
Examples
********

********
See Also
********

:php:func:`get_search_query_types`

:ref:`modelbrowsesql`

:ref:`search_query_types`