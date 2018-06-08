ASL Data Structure
==================

All the ASL widgets share a general purpose structure definition widget which allows you to describe the structure and acquisition
parameters of your ASL data, for example:

 - Whether your data is tag-control pairs, already subtracted or multi-phase
 - The ordering of the volume sequence in your data (e.g. whether tag-control pairs occur together, or whether all the tags come first)
 - Number of TIs/PLDs used and their values, bolus durations, number of repeats etc
 - Additional acquisition details, such as 2d/3d readout

In this section, we describe how to describe the structure of ASL data using this widget.

.. image:: screenshots/asl_struc.png

ASL data
########

This selects the data set whose structure you are defining. Once you define the structure of a data set in one ASL
widget, others will automatically pick up the same structure when using that data set. In addition, if you save
the data set to a Nifti file, the structure information is saved as optional metadata and will be recognised when
you load the data back into Quantiphyse.

Labelling format
################

The labelling can be described as Label-control pairs, Control-Label pairs, already tag-control subtracted or multiphase. Note that not all labelling methods are supported by all ASL widgets, for example to work with multiphase data you will need to preprocess it using the `Multiphase ASL widget <asl_multiphase.html>`_.

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
 
The data grouping box enables you to choose how the Tag-Control pairs, the repeats and the TIs are ordered in your data. You can use 
the Up/Down buttons to move the grouping order. To make this easier, a visualisation is shown below. For example the  ordering 
described above would be described as Repeats (outermost), TIs, TC pairs (innermost), and would be shown as follows:

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

.. image:: screenshots/asl_2d_readout.png

TI/PLD options
##############

The TIs or PLDs recorded in the ASL data must be specified, with the corresponding bolus durations. Initially data is 
interpreted as single-TI, however additional TIs can be added by typing their values into the blank space at the end of the TIs 
list. The list will automatically enlarge to fit the number of TIs and provide a new blank space to enter any further values.

.. image:: screenshots/asl_plds.png

If the number of PLDs specified is not consistent with the number of data volumes, a warning is displayed:

.. image:: screenshots/asl_plds_warning.png

Here we have specified a label-control dataset with 7 PLDs - this means the number of volumes should be a multiple of 14.

