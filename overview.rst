Overview
========

Quantiphyse works with two types of data:

 - 3D / 4D data sets. 
 
 - Regions of interest (ROIs). These must be 3D and contain integer data only. Voxels with the value zero are taken to be outside the 
   region of interest, nonzero values are inside. ROIs with more than one nonzero value describe multi-level regions of interest which
   are handled by some of the tools.

One data set is used as the main volume. This defaults to the first 4D data to be loaded, or the first data to be loaded,
however you can set any data set to be the main volume.

Data sets must have consistent dimensions to be loaded simultaneously. This means the first 3 dimensions must
match currently loaded data, and if the dataset is 4D, this must match any other 4D data sets loaded.

Special cases
-------------

Quantiphyse will try to handle some special cases which would otherwise prevent data being loaded and 
processed properly.

*Broken affine transformations*

Some data files may have incorrect file->world space transformations, meaning that although they do correspond
to other data the ordering of the dimensions is inconsistent. When loading data where dimensions are not
consistent, Quantiphyse will try ignoring the file transformation and take the data dimensions directly from
the file contents. If this enables the data to be loaded consistently, it will do so (with a warning).

*Multi-volume 2D data*

Some data files may contain 3 dimensions, but these should be interpreted as multiple 2D volumes (e.g. a time
series) rather than a single static 3D volume.

If a 3D data set is loaded first, an option is available to interpret the data as 2D multi-volumes. If 2D data 
is already loaded (either single or multiple volumes), subsequent 3D data sets will be interpreted as 2D 
multiple volume data sets if that enables them to be loaded (i.e. if the third dimension is consistent with
other loaded data sets).

Note that in Nifti files the first 3 dimensions are required to be spatial, so where this occurs with a Nifti
file it implies that the file is incorrectly formed and you should ideally correct the acquisition step which
produced it.

