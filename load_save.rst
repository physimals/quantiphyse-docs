=======================
Loading and Saving Data
=======================

File Formats
============

This software package works with NIFTI volumes. Some builds may contain experimental support for
folders of DICOM files, however this is not well tested.

Alternative packages which are able to convert DICOM files to NIFTI include the following: 

 - `itk-snap <http://www.itksnap.org/pmwiki/pmwiki.php>`_
 - `dcm2nii <https://www.nitrc.org/plugins/mwiki/index.php/dcm2nii:MainPage>`_
 - Or the batch version which allows a number of volumes to be converted 
   `dcm2niibatch <https://github.com/rordenlab/dcm2niix>`_

Loading data
============

Drag and drop
-------------

You can drag and drop single or multiple files onto the main window to load data. You will be prompted to 
choose the type of data:

.. image:: screenshots/drag_drop_choice.png

The suggested name is derived from the file name but is modified to ensure that it is a valid name
(data names must be valid Python variable names) and does not clash with any existing data.

If you choose a name which is the same as an existing data set, you will be asked if you wish to overwrite
the existing data. 

When dropping multiple files you will be asked to choose the type of each one. If you select *cancel* 
the data file will not be loaded.

Menu
----

The following menu option can be used to load data files:

 - File -> Load
 
.. image:: screenshots/file_menu.png

You will be prompted to choose the file type (data or ROI) and name in the same was as drag/drop.

Saving Data
===========

The following menu options are used for saving data:

- File -> Save current Overlay
- File -> Save current ROI

So, to save a data set you need to make it the current overlay, using the Overlay menu or the Volumes
widget. Similarly to save an ROI you need to make it the current ROI. Saving the main data can be 
done by selecting it as the current overlay.

Save a screen shot or plot
--------------------------

- Right click on an image or plot
- Click *Export*
- A view box will appear with the various format options. 
- *svg* format will allow editing of the layers and nodes in inkscape or another vector graphics viewer. 

.. image:: screenshots/export_image.png
