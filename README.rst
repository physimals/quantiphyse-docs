===========
Quantiphyse 
===========

Contributors

 - `Ben Irving <mailto:mail@birving.com>`_ (Original author)
 - `Martin Craig <mailto:martin.craig@eng.ox.ac.uk>`_ (Current maintainer)
 - `Michael Chappell <mailto:michael.chappell@eng.ox.ac.uk>`_
 
Quantiphyse is a viewing and analysis tool for 3D and 4D biomedical data. 

Features include:

 - 2D orthographic viewing and navigation of data, regions of interest (ROIs) and overlays
 - Generic analysis tools including clustering, supervoxel generation and curve comparison
 - Tools for DCE-MRI pharmacokinetic modelling
 - Tools for basic ROI generation
 - Extensible via plugins, including registration/motion correction, ASL and CEST MRI data and Bayesian modelling

Quantiphyse is not yet publically available although a release is planned in the near future.
Please contact the current maintainer `martin.craig@eng.ox.ac.uk <mailto:martin.craig@eng.ox.ac.uk>`_ if you wish 
to use the software

This documentation is based on the current development version, hence some of the information and screenshots
may be slightly out of date due to recent development work.

.. image:: screenshots/overlay_stats.jpg

License
-------
Licensing details will be added on first public release. The software will be free for non-commercial use.

User Guide
----------

.. toctree::
   :maxdepth: 2

   overview
   load_save
   interaction
   overlay_stats
   curve_compare
   compare
   cluster
   mean_values
   modelfit
   reg
   roibuilder
   sv
   t1
   pk
   simple_maths
   fabber
   cest
   asl
   veasl
   batch
   console

Images copyright 2016, 2017 Benjamin Irving

