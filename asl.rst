ASL Analysis
============

- *Widgets -> ASL -> Model fitting*

This widget provides Arterial Spin Labelling MRI analysis using the Fabber Bayesian model fitting framework.

ASL data structure
------------------

To do ASL model fitting you will need to define the structure of your ASL data, using the `ASL structure widget <asl_struc.rst>`_

Model fitting options
---------------------

For the model fitting, some additional information is required

.. image:: screenshots/asl_aquisition_options.png

In addition, a number of options may be specified for the model fitting process.

.. image:: screenshots/asl_analysis_options.png

  - ``Spatial regularization`` will smooth the data using an adaptive method which depends on the degree of variation in the data.
  - ``Allow uncertainty in T1 values`` will use the supplied T1 values as prior information, but allow some variation to fit the data better.
  - ``Include macro vascular component`` will allow an additional arterial component in the fitting process.
  - ``Fix bolus duration`` Normally the bolus duration is allowed some variation to better fit the data. Selecting this option will fix it to the user specified value.
  
.. warning::
    ``Spatial regularization`` prevents Fabber from processing voxels in parallel, hence the analysis will be much slower on multi-core systems.

Click ``Run`` to start the analysis. 

Output data
-----------

The following data items are returned:

  - ``perfusion`` Tissue perfusion
  - ``arrival`` Inferred bolus arrival time
  - ``modelfit`` Model prediction for comparison with the tag-control differenced data
  
If ``Include macro vascular component`` is specified:

  - ``mean_fblood``
  
If ``Allow uncertainty in T1 values`` is specified:

  - ``mean_T_1`` Tissue T1 value
  - ``mean_T_1b`` Blood T1 value

An example perfusion map ``mean_ftiss`` might look like this:

.. image:: screenshots/asl_ftiss.png


