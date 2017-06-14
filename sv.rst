Supervoxel widget
=================

This widget create supervoxels based a selected data map and a selected ROI.

Supervoxels are collections of voxels which are similar in terms of both data and also
spatial location. So, unlike clusters, supervoxels are always connected and localised.

Quantiphyse uses a novel supervoxel method based on SLIC, but modified so that it can
be applied sensibly to data within an ROI. For full method details see 
https://arxiv.org/abs/1606.09518v2

For 4D data, PCA analysis is initially performed to reduce the data to a 3D volume, as with
the 4D clustering widget. The number of PCA components can be specified to control this process.
For 3D data, the only preprocessing is a scaling of the data to the range 0-1 to enable 
parameters such as compactness to have consistent meaning.

The output is an ROI in which each supervoxel is an ROI region. This enables use with
for example, the mean values widget.

.. image:: screenshots/Selection_166.jpg
