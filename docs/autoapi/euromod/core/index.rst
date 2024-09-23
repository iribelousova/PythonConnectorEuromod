
euromod.core
============

.. py:module:: euromod.core


Below are listed the main public classes of the euromod.core module.






.. list-table:: **Classes**
   :header-rows: 0
   :widths: auto
   :class: summarytable

   * - :py:obj:`Country <euromod.core.Country>`
     - Country-specific EUROMOD tax-benefit model.
   * - :py:obj:`Dataset <euromod.core.Dataset>`
     - Dataset available in a country model.
   * - :py:obj:`DatasetInSystem <euromod.core.DatasetInSystem>`
     - Datasets available in a system model.
   * - :py:obj:`Extension <euromod.core.Extension>`
     - EUROMOD extensions.
   * - :py:obj:`ExtensionSwitch <euromod.core.ExtensionSwitch>`
     - \-
   * - :py:obj:`Function <euromod.core.Function>`
     - Functions implemented in a country policy.
   * - :py:obj:`FunctionInSystem <euromod.core.FunctionInSystem>`
     - Functions implemented in a policy for a specific system.
   * - :py:obj:`Model <euromod.core.Model>`
     - Base class of the Euromod Connector instantiating the microsimulation model
   * - :py:obj:`Parameter <euromod.core.Parameter>`
     - Parameters set up in a function.
   * - :py:obj:`ParameterInSystem <euromod.core.ParameterInSystem>`
     - Parameters set up in a function for a specific system.
   * - :py:obj:`Policy <euromod.core.Policy>`
     - Policy rules modeled in a country.
   * - :py:obj:`PolicyInSystem <euromod.core.PolicyInSystem>`
     - Policy rules modeled in a system.
   * - :py:obj:`ReferencePolicy <euromod.core.ReferencePolicy>`
     - Object storing the reference policies.
   * - :py:obj:`Simulation <euromod.core.Simulation>`
     - Object storing the simulation results.
   * - :py:obj:`System <euromod.core.System>`
     - A EUROMOD tax-benefit system.





.. toctree::
   :titlesonly:
   :maxdepth: 3


.. py:class:: Country(country: str, model: str)
   Bases: :py:obj:`base.Euromod_Element`

   Country-specific EUROMOD tax-benefit model.

   This class instantiates the EUROMOD tax benefit model for a given country.
   A class instance is automatically generated and stored in the attribute
   :obj:`countries` of the base class :class:`Model`.

   This class contains subclasses of type :class:`System`, :class:`Policy`,
   :class:`Dataset` and :class:`Extension`.

   .. rubric:: Example

   >>> from euromod import Model
   >>> mod=Model("C:\EUROMOD_RELEASES_I6.0+")
   >>> mod.countries[0]




   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`datasets <euromod.core.Country.datasets>`
        - A :obj:`Container` with :class:`Dataset` objects.
      * - :py:obj:`extensions <euromod.core.Country.extensions>`
        - A :obj:`Container` with :class:`Extension` objects. These are the local + model extensions defined.
      * - :py:obj:`local_extensions <euromod.core.Country.local_extensions>`
        - A :obj:`Container` with :class:`Extension` objects. These are the local extensions defined for the country.
      * - :py:obj:`model <euromod.core.Country.model>`
        - Returns the base :class:`Model` object.
      * - :py:obj:`name <euromod.core.Country.name>`
        - Two-letters country code.
      * - :py:obj:`policies <euromod.core.Country.policies>`
        - A :obj:`Container` with :class:`Policy` objects.
      * - :py:obj:`systems <euromod.core.Country.systems>`
        - A :obj:`Container` with :class:`System` objects.


   .. list-table:: Methods
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`get_switch_value <euromod.core.Country.get_switch_value>`\ (ext_name, dataset_name, sys_name)
        - :param ext_name: Name of the extension. The default is :obj:`None`.
      * - :py:obj:`load_data <euromod.core.Country.load_data>`\ (ID_DATASET, PATH_DATA)
        - Load data as a :class:`pandas.DataFrame` object.



   .. rubric:: Attributes

   .. py:attribute:: datasets
      :type:  container.Container[Dataset] | None
      :value: None


      A :obj:`Container` with :class:`Dataset` objects.

   .. py:attribute:: extensions
      :type:  container.Container[Extension] | None
      :value: None


      A :obj:`Container` with :class:`Extension` objects. These are the local + model extensions defined.

   .. py:attribute:: local_extensions
      :type:  container.Container[Extension] | None
      :value: None


      A :obj:`Container` with :class:`Extension` objects. These are the local extensions defined for the country.

   .. py:attribute:: model
      :type:  Model

      Returns the base :class:`Model` object.

      :type: "

   .. py:attribute:: name
      :type:  str

      Two-letters country code.

   .. py:attribute:: policies
      :type:  container.Container[Policy] | None
      :value: None


      A :obj:`Container` with :class:`Policy` objects.

   .. py:attribute:: systems
      :type:  container.Container[System] | None
      :value: None


      A :obj:`Container` with :class:`System` objects.


   .. rubric:: Methods
   
   .. py:method:: get_switch_value(ext_name: Optional[str] = None, dataset_name: Optional[str] = None, sys_name: Optional[str] = None)

      :param ext_name: Name of the extension. The default is :obj:`None`.
      :type ext_name: :obj:`str` , optional
      :param dataset_name: Name of the dataset. The default is :obj:`None`.
      :type dataset_name: :obj:`str` , optional
      :param sys_name: Name of the system. The default is :obj:`None`.
      :type sys_name: :obj:`str` , optional

      :raises KeyError: Is raised if ext_name, dataset_name or sys_name, but is not configured in the model.

      :returns: Object of the type :obj:`ExtensionSwitch` containing information how the switch is configured.
                Note that there is only a value returned if the switch is either explicitly 'off' or 'on'.
                When it's configured as n/a in the model no value will be included.
      :rtype: core.ExtensionSwitch


   
   .. py:method:: load_data(ID_DATASET, PATH_DATA=None)

      Load data as a :class:`pandas.DataFrame` object.

      :param ID_DATASET: Name of the dataset excluding extension (Note: must be a `txt` file).
      :type ID_DATASET: :obj:`str`
      :param PATH_DATA: Path to the dataset. Default is the PATH_TO_EUROMOD_PROJECT/Input folder.
      :type PATH_DATA: :obj:`str`, optional

      :returns: Dataset is returned as a :class:`pandas.DataFrame` object.
      :rtype: pandas.DataFrame



   


.. py:class:: Dataset(*args)
   Bases: :py:obj:`base.Euromod_Element`

   Dataset available in a country model.





   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`ID <euromod.core.Dataset.ID>`
        - Dataset identifier number.
      * - :py:obj:`coicopVersion <euromod.core.Dataset.coicopVersion>`
        - COICOP  version.
      * - :py:obj:`comment <euromod.core.Dataset.comment>`
        - Comment  about the dataset.
      * - :py:obj:`currency <euromod.core.Dataset.currency>`
        - Currency of the monetary values in the dataset.
      * - :py:obj:`decimalSign <euromod.core.Dataset.decimalSign>`
        - Decimal sign
      * - :py:obj:`name <euromod.core.Dataset.name>`
        - Name of the dataset.
      * - :py:obj:`private <euromod.core.Dataset.private>`
        - Access type.
      * - :py:obj:`readXVariables <euromod.core.Dataset.readXVariables>`
        - Read variables.
      * - :py:obj:`useCommonDefault <euromod.core.Dataset.useCommonDefault>`
        - Use default.
      * - :py:obj:`yearCollection <euromod.core.Dataset.yearCollection>`
        - Year of the dataset collection.
      * - :py:obj:`yearInc <euromod.core.Dataset.yearInc>`
        - Reference year for the income variables.




   .. rubric:: Attributes

   .. py:attribute:: ID
      :type:  str

      Dataset identifier number.

   .. py:attribute:: coicopVersion
      :type:  str
      :value: ''


      COICOP  version.

   .. py:attribute:: comment
      :type:  str
      :value: ''


      Comment  about the dataset.

   .. py:attribute:: currency
      :type:  str
      :value: ''


      Currency of the monetary values in the dataset.

   .. py:attribute:: decimalSign
      :type:  str
      :value: ''


      Decimal sign

   .. py:attribute:: name
      :type:  str

      Name of the dataset.

   .. py:attribute:: private
      :type:  str
      :value: 'no'


      Access type.

   .. py:attribute:: readXVariables
      :type:  str
      :value: 'no'


      Read variables.

   .. py:attribute:: useCommonDefault
      :type:  str
      :value: 'no'


      Use default.

   .. py:attribute:: yearCollection
      :type:  str

      Year of the dataset collection.

   .. py:attribute:: yearInc
      :type:  str

      Reference year for the income variables.



   


.. py:class:: DatasetInSystem
   Bases: :py:obj:`base.SystemElement`

   Datasets available in a system model.





   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`ID <euromod.core.DatasetInSystem.ID>`
        - Dataset identifier number.
      * - :py:obj:`bestMatch <euromod.core.DatasetInSystem.bestMatch>`
        - If yes, the current dataset is a best match for the specific system.
      * - :py:obj:`coicopVersion <euromod.core.DatasetInSystem.coicopVersion>`
        - COICOP  version.
      * - :py:obj:`comment <euromod.core.DatasetInSystem.comment>`
        - Comment  about the dataset.
      * - :py:obj:`currency <euromod.core.DatasetInSystem.currency>`
        - Currency of the monetary values in the dataset.
      * - :py:obj:`dataID <euromod.core.DatasetInSystem.dataID>`
        - Identifier number of the reference dataset at the country level.
      * - :py:obj:`decimalSign <euromod.core.DatasetInSystem.decimalSign>`
        - Decimal sign
      * - :py:obj:`name <euromod.core.DatasetInSystem.name>`
        - Name of the dataset.
      * - :py:obj:`private <euromod.core.DatasetInSystem.private>`
        - Access type.
      * - :py:obj:`readXVariables <euromod.core.DatasetInSystem.readXVariables>`
        - Read variables.
      * - :py:obj:`sysID <euromod.core.DatasetInSystem.sysID>`
        - Identifier number of the reference system.
      * - :py:obj:`useCommonDefault <euromod.core.DatasetInSystem.useCommonDefault>`
        - Use default.
      * - :py:obj:`yearCollection <euromod.core.DatasetInSystem.yearCollection>`
        - Year of the dataset collection.
      * - :py:obj:`yearInc <euromod.core.DatasetInSystem.yearInc>`
        - Reference year for the income variables.




   .. rubric:: Attributes

   .. py:attribute:: ID
      :type:  str

      Dataset identifier number.

   .. py:attribute:: bestMatch
      :type:  str

      If yes, the current dataset is a best match for the specific system.

   .. py:attribute:: coicopVersion
      :type:  str

      COICOP  version.

   .. py:attribute:: comment
      :type:  str

      Comment  about the dataset.

   .. py:attribute:: currency
      :type:  str

      Currency of the monetary values in the dataset.

   .. py:attribute:: dataID
      :type:  str

      Identifier number of the reference dataset at the country level.

   .. py:attribute:: decimalSign
      :type:  str

      Decimal sign

   .. py:attribute:: name
      :type:  str

      Name of the dataset.

   .. py:attribute:: private
      :type:  str

      Access type.

   .. py:attribute:: readXVariables
      :type:  str

      Read variables.

   .. py:attribute:: sysID
      :type:  str

      Identifier number of the reference system.

   .. py:attribute:: useCommonDefault
      :type:  str

      Use default.

   .. py:attribute:: yearCollection
      :type:  str

      Year of the dataset collection.

   .. py:attribute:: yearInc
      :type:  str

      Reference year for the income variables.



   


.. py:class:: Extension(*arg)
   Bases: :py:obj:`base.Euromod_Element`

   EUROMOD extensions.





   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`name <euromod.core.Extension.name>`
        - Full name of the extension.
      * - :py:obj:`shortName <euromod.core.Extension.shortName>`
        - Short name of the extension.




   .. rubric:: Attributes

   .. py:attribute:: name
      :type:  str
      :value: None


      Full name of the extension.

   .. py:attribute:: shortName
      :type:  str
      :value: None


      Short name of the extension.



   


.. py:class:: ExtensionSwitch(info, ctry)
   Bases: :py:obj:`base.Euromod_Element`

   





   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`data_name <euromod.core.ExtensionSwitch.data_name>`
        - Name of the applicable dataset
      * - :py:obj:`extension_name <euromod.core.ExtensionSwitch.extension_name>`
        - Short name of the extension
      * - :py:obj:`sys_name <euromod.core.ExtensionSwitch.sys_name>`
        - Name of the applicable system
      * - :py:obj:`value <euromod.core.ExtensionSwitch.value>`
        - value of the switch as configured in EUROOMOD.




   .. rubric:: Attributes

   .. py:attribute:: data_name

      Name of the applicable dataset

   .. py:attribute:: extension_name

      Short name of the extension

   .. py:attribute:: sys_name

      Name of the applicable system

   .. py:attribute:: value
      :value: ''


      value of the switch as configured in EUROOMOD.



   


.. py:class:: Function(*arg)
   Bases: :py:obj:`base.SpineElement`

   Functions implemented in a country policy.





   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`ID <euromod.core.Function.ID>`
        - Identifier number of the function.
      * - :py:obj:`comment <euromod.core.Function.comment>`
        - Comment specific to the function.
      * - :py:obj:`extensions <euromod.core.Function.extensions>`
        - A :obj:`Container` of :class:`Extension` objects in a country.
      * - :py:obj:`name <euromod.core.Function.name>`
        - Name of the function.
      * - :py:obj:`order <euromod.core.Function.order>`
        - Order of the function in the specific spine.
      * - :py:obj:`parameters <euromod.core.Function.parameters>`
        - A :obj:`Container` of :class:`Parameter` objects in a country.
      * - :py:obj:`polID <euromod.core.Function.polID>`
        - Identifier number of the reference policy.
      * - :py:obj:`private <euromod.core.Function.private>`
        - Access type.
      * - :py:obj:`spineOrder <euromod.core.Function.spineOrder>`
        - Order of the function in the spine.




   .. rubric:: Attributes

   .. py:attribute:: ID
      :type:  str

      Identifier number of the function.

   .. py:attribute:: comment
      :type:  str

      Comment specific to the function.

   .. py:attribute:: extensions
      :type:  container.Container[Extension] | None
      :value: None


      A :obj:`Container` of :class:`Extension` objects in a country.

   .. py:attribute:: name
      :type:  str

      Name of the function.

   .. py:attribute:: order
      :type:  str

      Order of the function in the specific spine.

   .. py:attribute:: parameters
      :type:  container.Container[Parameter] | None
      :value: None


      A :obj:`Container` of :class:`Parameter` objects in a country.

   .. py:attribute:: polID
      :type:  str

      Identifier number of the reference policy.

   .. py:attribute:: private
      :type:  str

      Access type.

   .. py:attribute:: spineOrder
      :type:  str

      Order of the function in the spine.



   


.. py:class:: FunctionInSystem(*arg)
   Bases: :py:obj:`base.SystemElement`

   Functions implemented in a policy for a specific system.





   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`ID <euromod.core.FunctionInSystem.ID>`
        - Identifier number of the function.
      * - :py:obj:`comment <euromod.core.FunctionInSystem.comment>`
        - Comment specific to the function.
      * - :py:obj:`extensions <euromod.core.FunctionInSystem.extensions>`
        - A :obj:`Container` of :class:`Extension` objects in a country.
      * - :py:obj:`funID <euromod.core.FunctionInSystem.funID>`
        - Identifier number of the reference function at country level.
      * - :py:obj:`name <euromod.core.FunctionInSystem.name>`
        - Name of the function.
      * - :py:obj:`order <euromod.core.FunctionInSystem.order>`
        - Order of the function in the specific spine.
      * - :py:obj:`parameters <euromod.core.FunctionInSystem.parameters>`
        - A :obj:`Container` with :class:`ParameterInSystem` objects specific to a function.
      * - :py:obj:`polID <euromod.core.FunctionInSystem.polID>`
        - Identifier number of the reference policy.
      * - :py:obj:`private <euromod.core.FunctionInSystem.private>`
        - Access type.
      * - :py:obj:`spineOrder <euromod.core.FunctionInSystem.spineOrder>`
        - Order of the function in the spine.
      * - :py:obj:`switch <euromod.core.FunctionInSystem.switch>`
        - Policy switch action.
      * - :py:obj:`sysID <euromod.core.FunctionInSystem.sysID>`
        - Identifier number of the reference policy.




   .. rubric:: Attributes

   .. py:attribute:: ID
      :type:  str

      Identifier number of the function.

   .. py:attribute:: comment
      :type:  str

      Comment specific to the function.

   .. py:attribute:: extensions
      :type:  container.Container[Extension]

      A :obj:`Container` of :class:`Extension` objects in a country.

   .. py:attribute:: funID
      :type:  str

      Identifier number of the reference function at country level.

   .. py:attribute:: name
      :type:  str

      Name of the function.

   .. py:attribute:: order
      :type:  str

      Order of the function in the specific spine.

   .. py:attribute:: parameters
      :type:  container.Container[ParameterInSystem] | None
      :value: None


      A :obj:`Container` with :class:`ParameterInSystem` objects specific to a function.

   .. py:attribute:: polID
      :type:  str

      Identifier number of the reference policy.

   .. py:attribute:: private
      :type:  str

      Access type.

   .. py:attribute:: spineOrder
      :type:  str

      Order of the function in the spine.

   .. py:attribute:: switch
      :type:  str

      Policy switch action.

   .. py:attribute:: sysID
      :type:  str

      Identifier number of the reference policy.



   


.. py:class:: Model(model_path: str)
   Bases: :py:obj:`base.Euromod_Element`

   Base class of the Euromod Connector instantiating the microsimulation model
   EUROMOD.

   :param model_path: Path to the EUROMOD project.
   :type model_path: :obj:`str`
   :param countries: Countries to load from the project folder. Names must be two-letter
                     country codes, see the Eurostat `Glossary:Country codes <https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:Country_codes>`_.
                     If omitted, will load all the available countries in the project folder.
                     Default is None.
   :type countries: :obj:`str`, or :obj:`Container` [ :obj:`str` ], optional

   :returns: A class containing the EUROMOD country models.
   :rtype: core.Model

   .. rubric:: Example

   >>> from euromod import Model
   >>> mod=Model("C:\EUROMOD_RELEASES_I6.0+")

   .. _Documentation:
       https://github.com/euromod/PythonIntegration/HOWTO.pdf




   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`countries <euromod.core.Model.countries>`
        - A :obj:`Container` with :class:`Country` objects.
      * - :py:obj:`emPath <euromod.core.Model.emPath>`
        - \-
      * - :py:obj:`errors <euromod.core.Model.errors>`
        - \-
      * - :py:obj:`extensions <euromod.core.Model.extensions>`
        - A :obj:`Container` with :class:`Model` extensions.
      * - :py:obj:`model_path <euromod.core.Model.model_path>`
        - Path to the EUROMOD project.




   .. rubric:: Attributes

   .. py:attribute:: countries
      :type:  container.Container[Country]

      A :obj:`Container` with :class:`Country` objects.

   .. py:attribute:: emPath

   .. py:attribute:: errors

   .. py:attribute:: extensions
      :type:  container.Container[Extension]

      A :obj:`Container` with :class:`Model` extensions.

   .. py:attribute:: model_path
      :type:  str

      Path to the EUROMOD project.



   


.. py:class:: Parameter(*arg)
   Bases: :py:obj:`base.SpineElement`

   Parameters set up in a function.





   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`ID <euromod.core.Parameter.ID>`
        - Identifier number of the parameter.
      * - :py:obj:`comment <euromod.core.Parameter.comment>`
        - Comment specific to the parameter.
      * - :py:obj:`extensions <euromod.core.Parameter.extensions>`
        - A :obj:`Container` with :class:`Extension` objects.
      * - :py:obj:`funID <euromod.core.Parameter.funID>`
        - Identifier number of the reference function at country level.
      * - :py:obj:`group <euromod.core.Parameter.group>`
        - Parameter group value.
      * - :py:obj:`name <euromod.core.Parameter.name>`
        - Name of the parameter.
      * - :py:obj:`order <euromod.core.Parameter.order>`
        - Order of the parameter in the specific spine.
      * - :py:obj:`spineOrder <euromod.core.Parameter.spineOrder>`
        - Order of the parameter in the spine.




   .. rubric:: Attributes

   .. py:attribute:: ID
      :type:  str

      Identifier number of the parameter.

   .. py:attribute:: comment
      :type:  str

      Comment specific to the parameter.

   .. py:attribute:: extensions
      :type:  container.Container[Extension] | None
      :value: None


      A :obj:`Container` with :class:`Extension` objects.

   .. py:attribute:: funID
      :type:  str

      Identifier number of the reference function at country level.

   .. py:attribute:: group
      :type:  str
      :value: ''


      Parameter group value.

      :type: str

   .. py:attribute:: name
      :type:  str

      Name of the parameter.

   .. py:attribute:: order
      :type:  str

      Order of the parameter in the specific spine.

   .. py:attribute:: spineOrder
      :type:  str

      Order of the parameter in the spine.



   


.. py:class:: ParameterInSystem
   Bases: :py:obj:`base.SystemElement`

   Parameters set up in a function for a specific system.





   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`ID <euromod.core.ParameterInSystem.ID>`
        - Identifier number of the parameter.
      * - :py:obj:`comment <euromod.core.ParameterInSystem.comment>`
        - Comment specific to the parameter.
      * - :py:obj:`extensions <euromod.core.ParameterInSystem.extensions>`
        - A :obj:`Container` with :class:`Extension` objects.
      * - :py:obj:`funID <euromod.core.ParameterInSystem.funID>`
        - Identifier number of the reference function at country level.
      * - :py:obj:`group <euromod.core.ParameterInSystem.group>`
        - Parameter group number.
      * - :py:obj:`name <euromod.core.ParameterInSystem.name>`
        - Name of the parameter.
      * - :py:obj:`order <euromod.core.ParameterInSystem.order>`
        - Order of the parameter in the specific spine.
      * - :py:obj:`parID <euromod.core.ParameterInSystem.parID>`
        - Identifier number of the reference parameter at country level.
      * - :py:obj:`spineOrder <euromod.core.ParameterInSystem.spineOrder>`
        - Order of the parameter in the spine.
      * - :py:obj:`sysID <euromod.core.ParameterInSystem.sysID>`
        - Identifier number of the reference system.
      * - :py:obj:`value <euromod.core.ParameterInSystem.value>`
        - Value of the parameter.




   .. rubric:: Attributes

   .. py:attribute:: ID
      :type:  str

      Identifier number of the parameter.

   .. py:attribute:: comment
      :type:  str

      Comment specific to the parameter.

   .. py:attribute:: extensions
      :type:  list

      A :obj:`Container` with :class:`Extension` objects.

   .. py:attribute:: funID
      :type:  str

      Identifier number of the reference function at country level.

   .. py:attribute:: group
      :type:  str

      Parameter group number.

      :type: str

   .. py:attribute:: name
      :type:  str

      Name of the parameter.

   .. py:attribute:: order
      :type:  str

      Order of the parameter in the specific spine.

   .. py:attribute:: parID
      :type:  str

      Identifier number of the reference parameter at country level.

   .. py:attribute:: spineOrder
      :type:  str

      Order of the parameter in the spine.

   .. py:attribute:: sysID
      :type:  str

      Identifier number of the reference system.

   .. py:attribute:: value
      :type:  str

      Value of the parameter.



   


.. py:class:: Policy(*arg)
   Bases: :py:obj:`base.SpineElement`

   Policy rules modeled in a country.





   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`ID <euromod.core.Policy.ID>`
        - Identifier number of the policy.
      * - :py:obj:`comment <euromod.core.Policy.comment>`
        - Comment specific to the policy.
      * - :py:obj:`extensions <euromod.core.Policy.extensions>`
        - A :obj:`Container` of policy-specific :class:`Extension` objects.
      * - :py:obj:`functions <euromod.core.Policy.functions>`
        - A :obj:`Container` of policy-specific :class:`Function` objects.
      * - :py:obj:`name <euromod.core.Policy.name>`
        - Name of the policy.
      * - :py:obj:`order <euromod.core.Policy.order>`
        - Order of the policy in the specific spine.
      * - :py:obj:`private <euromod.core.Policy.private>`
        - Access type. Default is 'no'.
      * - :py:obj:`spineOrder <euromod.core.Policy.spineOrder>`
        - Order of the policy in the spine.




   .. rubric:: Attributes

   .. py:attribute:: ID
      :type:  str

      Identifier number of the policy.

   .. py:attribute:: comment
      :type:  str

      Comment specific to the policy.

   .. py:attribute:: extensions
      :type:  container.Container[Extension] | None
      :value: None


      A :obj:`Container` of policy-specific :class:`Extension` objects.

   .. py:attribute:: functions
      :type:  container.Container[Function] | None
      :value: None


      A :obj:`Container` of policy-specific :class:`Function` objects.

   .. py:attribute:: name
      :type:  str

      Name of the policy.

   .. py:attribute:: order
      :type:  str

      Order of the policy in the specific spine.

   .. py:attribute:: private
      :type:  str
      :value: 'no'


      Access type. Default is 'no'.

   .. py:attribute:: spineOrder
      :type:  str

      Order of the policy in the spine.



   


.. py:class:: PolicyInSystem(*arg)
   Bases: :py:obj:`base.SystemElement`

   Policy rules modeled in a system.





   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`ID <euromod.core.PolicyInSystem.ID>`
        - Identifier number of the policy.
      * - :py:obj:`comment <euromod.core.PolicyInSystem.comment>`
        - Comment specific to the policy.
      * - :py:obj:`extensions <euromod.core.PolicyInSystem.extensions>`
        - A :obj:`Container` of policy-specific :class:`Extension` objects.
      * - :py:obj:`functions <euromod.core.PolicyInSystem.functions>`
        - A :obj:`Container` with :class:`FunctionInSystem` objects specific to the system
      * - :py:obj:`name <euromod.core.PolicyInSystem.name>`
        - Name of the policy.
      * - :py:obj:`order <euromod.core.PolicyInSystem.order>`
        - Order of the policy in the specific spine.
      * - :py:obj:`polID <euromod.core.PolicyInSystem.polID>`
        - Identifier number of the reference policy at country level.
      * - :py:obj:`private <euromod.core.PolicyInSystem.private>`
        - Access type. Default is 'no'.
      * - :py:obj:`spineOrder <euromod.core.PolicyInSystem.spineOrder>`
        - Order of the policy in the spine.
      * - :py:obj:`switch <euromod.core.PolicyInSystem.switch>`
        - Policy switch action.
      * - :py:obj:`sysID <euromod.core.PolicyInSystem.sysID>`
        - Identifier number of the reference system.




   .. rubric:: Attributes

   .. py:attribute:: ID
      :type:  str

      Identifier number of the policy.

   .. py:attribute:: comment
      :type:  str

      Comment specific to the policy.

   .. py:attribute:: extensions
      :type:  container.Container[Extension]

      A :obj:`Container` of policy-specific :class:`Extension` objects.

   .. py:attribute:: functions
      :type:  container.Container[FunctionInSystem] | None
      :value: None


      A :obj:`Container` with :class:`FunctionInSystem` objects specific to the system

   .. py:attribute:: name
      :type:  str

      Name of the policy.

   .. py:attribute:: order
      :type:  str

      Order of the policy in the specific spine.

   .. py:attribute:: polID
      :type:  str

      Identifier number of the reference policy at country level.

   .. py:attribute:: private
      :type:  str

      Access type. Default is 'no'.

   .. py:attribute:: spineOrder
      :type:  str

      Order of the policy in the spine.

   .. py:attribute:: switch
      :type:  str

      Policy switch action.

   .. py:attribute:: sysID
      :type:  str

      Identifier number of the reference system.



   


.. py:class:: ReferencePolicy(info, parent)
   Bases: :py:obj:`base.SpineElement`

   Object storing the reference policies.




   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`extensions <euromod.core.ReferencePolicy.extensions>`
        - A :obj:`Container` of reference policy-specific :class:`Extension` objects.
      * - :py:obj:`name <euromod.core.ReferencePolicy.name>`
        - Name of the reference policy.




   .. rubric:: Attributes

   .. py:attribute:: extensions
      :type:  container.Container[Extension] | None
      :value: None


      A :obj:`Container` of reference policy-specific :class:`Extension` objects.

   .. py:attribute:: name
      :type:  str

      Name of the reference policy.



   


.. py:class:: Simulation(out, constantsToOverwrite)
   Bases: :py:obj:`base.Euromod_Element`

   Object storing the simulation results.

   This is a class containing results from the simulation :obj:`run`
   and other related configuration information.




   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`constantsToOverwrite <euromod.core.Simulation.constantsToOverwrite>`
        - A :obj:`dict`-type object with user-defined constants.
      * - :py:obj:`errors <euromod.core.Simulation.errors>`
        - A :obj:`list` with errors and warnings from the simulation run.
      * - :py:obj:`output_filenames <euromod.core.Simulation.output_filenames>`
        - A :obj:`list` of file-names of simulation output.
      * - :py:obj:`outputs <euromod.core.Simulation.outputs>`
        - A :obj:`Container` with type :class:`pandas.DataFrame` simulation results.




   .. rubric:: Attributes

   .. py:attribute:: constantsToOverwrite
      :type:  dict[tuple(str, str), str]

      A :obj:`dict`-type object with user-defined constants.

   .. py:attribute:: errors
      :type:  list[str]

      A :obj:`list` with errors and warnings from the simulation run.

   .. py:attribute:: output_filenames
      :type:  list[str] | []
      :value: []


      A :obj:`list` of file-names of simulation output.

   .. py:attribute:: outputs
      :type:  container.Container[pandas.DataFrame]

      A :obj:`Container` with type :class:`pandas.DataFrame` simulation results.
      For indexing use an integer or a label from :obj:`output_filenames`.



   


.. py:class:: System(*arg)
   Bases: :py:obj:`base.Euromod_Element`

   A EUROMOD tax-benefit system.

   This class represents a EUROMOD tax system.
   Instances of this class are generated automatically when loading a EUROMOD model and are contained in the
   `systems` Contaiber which is an attribute of the :class:`Country`.


   .. rubric:: Example

   >>> from euromod import Model
   >>> mod=Model("C:\EUROMOD_RELEASES_I6.0+")
   >>> mod.countries[0].systems[-1]




   .. rubric:: Overview

   .. list-table:: Attributes
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`ID <euromod.core.System.ID>`
        - Identifier number of the system.
      * - :py:obj:`bestmatch_datasets <euromod.core.System.bestmatch_datasets>`
        - A :obj:`Container` with best-match :class:`Dataset` objects in the system.
      * - :py:obj:`comment <euromod.core.System.comment>`
        - Comment specific to the system.
      * - :py:obj:`currencyOutput <euromod.core.System.currencyOutput>`
        - Currency of the simulation results.
      * - :py:obj:`currencyParam <euromod.core.System.currencyParam>`
        - Currency of the monetary parameters in the system.
      * - :py:obj:`datasets <euromod.core.System.datasets>`
        - A :obj:`Container` of :class:`DatasetInSystem` objects in the system.
      * - :py:obj:`headDefInc <euromod.core.System.headDefInc>`
        - Main income definition.
      * - :py:obj:`name <euromod.core.System.name>`
        - Name of the system.
      * - :py:obj:`order <euromod.core.System.order>`
        - System order in the spine.
      * - :py:obj:`policies <euromod.core.System.policies>`
        - A :obj:`Container` of :class:`PolicyInSystem` objects in the system.
      * - :py:obj:`private <euromod.core.System.private>`
        - Access type.
      * - :py:obj:`year <euromod.core.System.year>`
        - System year.


   .. list-table:: Methods
      :header-rows: 0
      :widths: auto
      :class: summarytable

      * - :py:obj:`run <euromod.core.System.run>`\ (data, dataset_id, constantsToOverwrite, verbose, outputpath, addons, switches, nowarnings, euro, public_components_only)
        - Run the simulation of a EUROMOD tax-benefit system.



   .. rubric:: Attributes

   .. py:attribute:: ID
      :type:  str

      Identifier number of the system.

   .. py:attribute:: bestmatch_datasets
      :type:  container.Container[Dataset] | None
      :value: None


      A :obj:`Container` with best-match :class:`Dataset` objects in the system.

   .. py:attribute:: comment
      :type:  str

      Comment specific to the system.

   .. py:attribute:: currencyOutput
      :type:  str

      Currency of the simulation results.

   .. py:attribute:: currencyParam
      :type:  str

      Currency of the monetary parameters in the system.

   .. py:attribute:: datasets
      :type:  container.Container[DatasetInSystem] | None
      :value: None


      A :obj:`Container` of :class:`DatasetInSystem` objects in the system.

   .. py:attribute:: headDefInc
      :type:  str

      Main income definition.

   .. py:attribute:: name
      :type:  str

      Name of the system.

   .. py:attribute:: order
      :type:  str

      System order in the spine.

   .. py:attribute:: policies
      :type:  container.Container[PolicyInSystem] | None
      :value: None


      A :obj:`Container` of :class:`PolicyInSystem` objects in the system.

   .. py:attribute:: private
      :type:  str

      Access type.

   .. py:attribute:: year
      :type:  str

      System year.


   .. rubric:: Methods
   
   .. py:method:: run(data: pandas.DataFrame, dataset_id: str, constantsToOverwrite: Optional[Dict[Tuple[str, str], str]] = None, verbose: bool = True, outputpath: str = '', addons: List[Tuple[str, str]] = [], switches: List[Tuple[str, bool]] = [], nowarnings=False, euro=False, public_components_only=False)

      Run the simulation of a EUROMOD tax-benefit system.


      :param data: input dataframe passed to the EUROMOD model.
      :type data: :class:`pandas.DataFrame`
      :param dataset_id: ID of the dataset.
      :type dataset_id: :obj:`str`
      :param constantsToOverwrite: A :obj:`list` of constants to overwrite. Note that the key is a tuple for which the first element is the name of the constant and the second string the groupnumber
                                   Default is :obj:`None`.
      :type constantsToOverwrite: :obj:`dict` [ :obj:`tuple` [ :obj:`str`, :obj:`str` ], :obj:`str` ], optional
      :param verbose: If True then information on the output will be printed. Default is :obj:`True`.
      :type verbose: :obj:`bool`, optional
      :param outputpath: When an output path is provided, there will be anoutput file generated. Default is "".
      :type outputpath: :obj:`str`, optional
      :param addons: :obj:`list` of addons to be integrated in the spine, where the first element of the tuple is the name of the Addon
                     and the second element is the name of the system in the Addon to be integrated. Default is [].
      :type addons: :obj:`list` [ :obj:`tuple` [ :obj:`str`, :obj:`str` ]], optional
      :param switches: :obj:`list` of Extensions to be switched on or of. The first element of the tuple is the short name of the Addon.
                       The second element is a boolean Default is [].
      :type switches: :obj:`list` [ :obj:`tuple` [ :obj:`str`, :obj:`bool` ]], optional
      :param nowarnings: If True, the warning messages resulting from the simulations will be suppressed. Default is :obj:`False`.
      :type nowarnings: :obj:`bool`, optional
      :param euro: If True then the monetary variables in the output will be converted to euro. Default value is :obj:`False`.
      :type euro: :obj:`bool`, optional
      :param public_compoments_only: If True then the the model will be on with only the public compoments. Default value is :obj:`False`.
      :type public_compoments_only: :obj:`bool`, optional

      :raises Exception: Exception when simulation does not finish succesfully, i.e. without errors.

      :returns: A class containing simulation output and error messages.
      :rtype: core.Simulation

      .. rubric:: Example

      >>> # Load the dataset
      >>> import pandas as pd
      >>> data = pd.read_csv("C:\EUROMOD_RELEASES_I6.0+\Input\sl_demo_v4.txt",sep="   ")
      >>> # Load EUROMOD
      >>> from euromod import Model
      >>> mod=Model("C:\EUROMOD_RELEASES_I6.0+")
      >>> # Run simulation
      >>> out=mod.countries['SL'].systems['SL_1996'].run(data,'sl_demo_v4')



   





