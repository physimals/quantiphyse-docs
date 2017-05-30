Curve clustering
================

The curve clustering widget allows PCA based clustering of 3D ROI regions based on a 4D volume sequence
(e.g. DCE enhancement curves)

Options
-------

- Number of clusters, i.e. how many subregions the ROI will be split into
- Number of PCA modes used for clustering

On clicking ``Run``, a new ROI named ``clusters`` is produced, and the median enhancement curves are displayed.

Advanced options
----------------

Having generated clusters, it may be desirable to merge some of the subregions - for example if two are
very similar, or one contains very few voxels. The ``Merge`` tool allows you to do this by specifying the
two regions to be merged.

To help with this, a voxel count can be displayed using the ``Voxel Count`` button.

An ``Auto Merge`` tool is also provided to automatically identify subregions for merging.

.. image:: screenshots/10.png
