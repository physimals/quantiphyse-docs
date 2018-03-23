===========
|qplogo| Quantiphyse 
===========

.. |qplogo| image:: screenshots/qp_logo.png 
    :height: 48px

Contributors

 - `Martin Craig <mailto:martin.craig@eng.ox.ac.uk>`_ (Current maintainer)
 - `Ben Irving <mailto:mail@birving.com>`_ (Original author)
 - `Michael Chappell <mailto:michael.chappell@eng.ox.ac.uk>`_
 - Paula Croal

Quantiphyse is a viewing and analysis tool for 3D and 4D biomedical data. It is particularly suited for physioligcal or functional imaging data comprised of multi volumes in a 4D (time-) series and/or multimodal imaging data. Quantiphyse is built around the concept of making spatially resolved measurements of physical or physiological processes from imaging data using either model-based or model-free methods, in a large part exploiting Bayesian inference techniques. Quantiphyse can analyse data both voxelwise or within regions of interest that may be manually or automatically created, e.g. supervoxel or clustering methods. 

Features include:

 - 2D orthographic viewing and navigation of data, regions of interest (ROIs) and overlays
 - Universal analysis tools including clustering, supervoxel generation and curve comparison
 - Tools for DCE-MRI pharmacokinetic modelling
 - Tools for ROI generation
 - Extensible via plugins, including registration/motion correction, ASL and CEST MRI data and Bayesian modelling

Quantiphyse will soon be available via the `Oxford University Innovation Software 
Store <https://process.innovation.ox.ac.uk/software>`_ 

This documentation is based on the upcoming release version 0.4.

.. image:: screenshots/sample_image.png

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
   
Current included plugins
===============

.. toctree::
   :maxdepth: 1

   t1
   pk
   cest
   fabber

Advanced Tools
==============

.. toctree::
   :maxdepth: 1

   batch
   console
   
Images copyright 2018 University of Oxford

