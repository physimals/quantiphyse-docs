ASL Calibration
===============

- *Widgets -> ASL Calibration*

The ASL Calibration widget is required to turn the perfusion images from ASL model fitting into physical units.

Basic data specification
------------------------

.. image:: screenshots/asl_calib_data.png

To do calibration you specify a data set containing a perfusion image. If you want to calibrate an image containing perfusion
variance, the ``Data type`` selection must be changed (because the scaling factors must be squared in this case).

Calibration methods
-------------------

Two calibration methods are provided:

- ``Voxelwise`` calibration, in which an M0 correction factor is determined for each voxel from the calibration image.
- ``Reference region`` calibration, in which a single M0 correction factor is determined for the whole image, by analysing a 
  region of the data containing a single tissue type (typically CSF).
  
Calibration data
----------------

Certain parameters are required regardless of which calibration method you use:

.. image:: screenshots/asl_calib_calibdata.png

Voxelwise calibration
---------------------

.. image:: screenshots/asl_calib_voxelwise.png

Reference region calibration
---------------------

.. image:: screenshots/asl_calib_refregion.png
