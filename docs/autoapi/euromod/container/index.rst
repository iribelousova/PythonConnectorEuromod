
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
   via keys that are the name of the objects
   or via integer indexing as in a list.




   .. rubric:: Overview


   .. list-table:: Methods
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`find <euromod.container.Container.find>`\ (key, pattern, return_children, case_insentive)
        - Search for object attributes by pattern.




   .. rubric:: Methods
   
   .. py:method:: find(key, pattern, return_children=False, case_insentive=True)

      Search for object attributes by pattern.

      :param key: Name of the attribute or the attribute of a child element that you want to look for.
                  One can search child elements by using the dot-notation.
                  E.g.: mod["BE"]["BE_2023"].policies.find("functions.name","BenCalc")
      :type key: :obj:`str`
      :param pattern: Pattern that you want to match.
      :type pattern: :obj:`str`
      :param return_children: When True, the return type will be a :obj:`Container` containing elements of the type for which the find method was used
                              When False, the return type will be a :obj:`Container` of the elements of the deepest level specified by the pattern key-word.
                              E.g.: mod["BE"]["BE_2023"].policies.find("function)
                              The default is :obj:`False`.
      :type return_children: :obj:`bool`, optional
      :param case_insentive: When false, perform case-insensitive matching. The default is :obj:`True`.
      :type case_insentive: :obj:`bool`, optional

      :returns: A container of objects that matched the pattern.
      :rtype: container.Container



   





