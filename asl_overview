ASL Analysis
============

- *Widgets -> ASL*

A number of widgets are provided for use in processing Arterial Spin Labelling MRI analysis using the Fabber Bayesian model 
fitting framework.

 - ASL preprocessing - basic preprocessing of ASL data such as tag-control subtraction and generation of perfusion-weighted images
 - ASL model fitting - Bayesian model fitting for ASL data generating parameter maps for perfusion, arrival time and other parameters
 - `Multiphase ASL multiphase_asl`_ - Pre-processing step for multiphase ASL producing output suitable for standard ASL model fitting
 
Defining the basic ASL data structure
--------------------

All the ASL widgets share a general purpose structure definition widget which allows you to describe the structure and acquisition
parameters of your ASL data, for example:

 - Whether your data is tag-control pairs, already subtracted or multi-phase
 - The ordering of the volume sequence in your data (e.g. whether tag-control pairs occur together, or whether all the tags come first)
 - Number of TIs/PLDs used and their values, bolus durations, number of repeats etc
 - Additional acquisition details, such as 2d/3d readout

In this section, we describe how to describe the structure of ASL data using this widget.

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

The TIs or PLDs recorded in the ASL data must be specified, with the corresponding bolus durations. Initially data is 
interpreted as single-TI, however additional TIs can be added by typing their values into the blank space at the end of the TIs 
list. The list will automatically enlarge to fit the number of TIs and provide a new blank space to enter any further values.

