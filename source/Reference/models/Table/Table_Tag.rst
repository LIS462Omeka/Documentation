---------
Table_Tag
---------

.. php:class:: Table_Tag

extends :php:class:`Omeka_Db_Table`

    .. php:method:: findOrNew($name)

        :param $name:

    .. php:method:: filterByRecord($select, $record)

        Filter a SELECT statement based on an Omeka_Record_AbstractRecord instance

        :param $select:
        :param $record:
        :returns: void

    .. php:method:: applySorting($select, $sortField, $sortDir)

        Apply custom sorting for tags.

        This also applies the normal, built-in sorting.

        :type $select: Omeka_Db_Select
        :param $select:
        :type $sortField: string
        :param $sortField: Sorting field.
        :type $sortDir: string
        :param $sortDir: Sorting direction, suitable for direct inclusion in SQL (ASC or DESC).

    .. php:method:: filterByTagType($select, $type)

        Filter SELECT statement based on the type of tags to view (Item, Exhibit,
        etc.)

        :param $select:
        :param $type:
        :returns: void

    .. php:method:: filterByTagNameLike($select, $partialTagName)

        Filter SELECT statement based on whether the tag contains the partial tag
        name

        :param $select:
        :param $partialTagName:
        :returns: void

    .. php:method:: applySearchFilters($select, $params = array())

        Retrieve a certain number of tags

        :param $select:
        :type $params: array
        :param $params: 'limit' => integer 'record' => instanceof Omeka_Record_AbstractRecord 'like' => partial_tag_name 'type' => tag_type
        :returns: void

    .. php:method:: getSelect()

        :returns: Omeka_Db_Select

    .. php:method:: findTagNamesLike($partialName, $limit = 10)

        :param $partialName:
        :param $limit:
