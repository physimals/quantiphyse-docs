===========
Quantiphyse 
===========

Contributors

 - `Martin Craig <mailto:martin.craig@eng.ox.ac.uk>`_ (Current maintainer)
 - `Ben Irving <mailto:mail@birving.com>`_ (Original author)
 - `Michael Chappell <mailto:michael.chappell@eng.ox.ac.uk>`_
 
Quantiphyse is a viewing and analysis tool for 3D and 4D biomedical data. 

Features include:

 - 2D orthographic viewing and navigation of data, regions of interest (ROIs) and overlays
 - Generic analysis tools including clustering, supervoxel generation and curve comparison
 - Tools for DCE-MRI pharmacokinetic modelling
 - Tools for basic ROI generation
 - Extensible via plugins, including registration/motion correction, ASL and CEST MRI data and Bayesian modelling

Quantiphyse will soon be available via the `Oxford University Innovation Software 
Store <https://process.innovation.ox.ac.uk/software>`_ 

This documentation is based on the upcoming release version 0.4.

.. image:: screenshots/overlay_stats.jpg

License
-------
Licensing details will be added on first public release. The software will be free for non-commercial use.

Bugs/Issues
-----------

Please report bug, issues, feature requests or other comments to the  `current maintainer: <mailto:martin.craig@eng.ox.ac.uk>`_

User Guide
----------

Basic functions
===============

.. toctree::
   :maxdepth: 2

   overview
   load_save
   interaction
   overlay_stats
   
Generic analysis and processing tools
===============

.. toctree::
   :maxdepth: 1

   modelfit
   compare
   curve_compare
   simple_maths
   reg
   smoothing
   cluster
   sv
   roi_analysis
   roibuilder
   mean_values
   batch
   console
   
Current included plugins
===============

.. toctree::
   :maxdepth: 1

   t1
   pk
   fabber
   cest

Images copyright 2016, 2017 Benjamin Irving

