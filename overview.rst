Overview
========

Quantiphyse works with three types of image:

 - The main volume. This is typically a 4D data set and defines the dimensions of the data. All other images must have consistent
   dimensions. Only one main volume can be loaded, if a new main volume is loaded all other data will be cleared.
 
 - Overlays. These may be 3D or 4D, if they are 4D the fourth dimension must currently match the 4th dimension of the main volume. They are viewed as colour images on top of the main volume.
 
 - Regions of Interest (ROIs). These must be 3D and contain integer data only. Voxels with the value zero are taken to be outside the 
   region of interest, nonzero values are inside. ROIs with more than one nonzero value describe multi-level regions of interest which
   are handled by some of the tools in PkView.
