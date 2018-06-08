ASL Analysis
============

- *Widgets -> ASL -> Model fitting*

This widget provides Arterial Spin Labelling MRI analysis using the Fabber Bayesian model fitting framework.

To do ASL analysis you will need to know the following:

 - Whether your data is tag-control pairs, already subtracted or multi-phase
 - The ordering of the volume sequence in your data (e.g. whether tag-control pairs occur together, or whether all the tags come first)
 - Details of the aquisition sequence (e.g. number of TIs/PLDs used and their values, bolus durations, number of repeats etc)

Basic data structure
--------------------

Before any ASL processing can occur, the basic structure of the input data must be defined.

.. image:: screenshots/asl_preprocess_options.png

Labelling format
################

The labelling can be described as Tag-control pairs, Control-Tag pairs, already tag-control subtracted or multiphase. Note that this widget does not support multiphase data, however an alternative ASL widget allows multiphase data to be preprocessed for subsequent model fitting.

Data grouping/order
###################

This describes the sequence of volumes contained in the ASL data set, and what each volume contains. For example the sequence of volumes in your data might be as follows:

 - Tag for first TI
 - Control for first TI
 - Tag for second TI
 - Control for second TI
 - ... as above for remaining TIs
 - Repeat of Tag for first TI
 - Repeat of Control for first TI
 - ... etc
 
The data grouping box enables you to choose how the Tag-Control pairs, the repeats and the TIs are ordered in your data. You can drag the items in the list to reorder them, or use the Up/Down buttons. To make this easier, a visualisation is shown below. For example the  ordering described above would be described as Repeats (outermost), TIs, TC pairs (innermost), and would be shown as follows:

.. image:: screenshots/asl_grouping_rtp.png

Alternatively the same data might be in a different order:

 - Control for first TI
 - Control for second TI
 - ... as above for remaining TIs
 - Tag for first TI
 - Tag for second TI
 - ... as above for remaining TIs
 - Repeat of Control for first TI
 - Repeat of Control for second TI
 - ... etc

This would be described as Repeats (outermost), CT pairs, TIs (innermost), and would be shown as follows:

.. image:: screenshots/asl_grouping_rpt.png

Labelling method
################

The labelling method is either cASL/pcASL or pASL. In cASL/pcASL, the effective TI for each volume is determined by adding the post-labelling delay (PLD) to the bolus duration. In pASL, the TIs are specified directly.

Readout options
###############

If the readout was 2D, the delay time per slice can be specified to enable the timing of each slice to be determined more accurately. It is also possible to specify a multiband readout.

TI/PLD options
##############

The TIs or PLDs recorded in the ASL data must be specified, with the corresponding bolus durations.

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


