
euromod.container
=================

.. py:module:: euromod.container


Below are listed the main public classes of the euromod.container module.






.. list-table:: **Classes**
   :header-rows: 0
   :widths: auto
   :class: summarytable

   * - :py:obj:`Container <euromod.container.Container>`
     - This class is a container for objects that allow for indexing and representation in multiple ways:





.. toctree::
   :titlesonly:
   :maxdepth: 3


.. py:class:: Container(idDict=False)
   This class is a container for objects that allow for indexing and representation in multiple ways:
   - via keys that are the name of the objects or,
   - via integer indexing as in a list.




   .. rubric:: Overview


   .. list-table:: Methods
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`find <euromod.container.Container.find>`\ (key, pattern, return_children, case_insentive)
        - Find objects that match pattern.
      * - :py:obj:`items <euromod.container.Container.items>`\ ()
        - Get items of the :class:`Container`.
      * - :py:obj:`keys <euromod.container.Container.keys>`\ ()
        - Get keys of the :class:`Container`.
      * - :py:obj:`values <euromod.container.Container.values>`\ ()
        - Get values of the :class:`Container`.




   .. rubric:: Methods
   
   .. py:method:: find(key, pattern, return_children=False, case_insentive=True)

      Find objects that match pattern.

      :param key: Name of the attribute or the attribute of a child element that you want to look for
                  One can search child elements by using the dot-notation.
                  E.g.: mod["BE"]["BE_2023"].policies.find("functions.name","BenCalc")
      :type key: :obj:`str`
      :param pattern: pattern that you want to match.
      :type pattern: :obj:`str`
      :param return_children: When True, the return type will be a Container containing elements of the type for which the find method was used
                              When False, the return type will be a Container of the elements of the deepest level specified by the pattern key-word.
                              E.g.: mod["BE"]["BE_2023"].policies.find("function)
                              The default is False.
      :type return_children: bool, optional
      :param case_insentive: DESCRIPTION. The default is True.
      :type case_insentive: :obj:`bool`, optional

      :returns: An object that matches the pattern.
      :rtype: Container


   
   .. py:method:: items()

      Get items of the :class:`Container`.

      :returns: Object items.
      :rtype: :obj:`Container.items`


   
   .. py:method:: keys()

      Get keys of the :class:`Container`.

      :returns: Names of the attribute or the attribute of a child element.
      :rtype: :obj:`Container.keys`


   
   .. py:method:: values()

      Get values of the :class:`Container`.

      :returns: Value of the object attribute.
      :rtype: :obj:`Container.values`



   





