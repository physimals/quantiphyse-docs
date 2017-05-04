Supervoxel widget
=================

This widget create supervoxels based on the data within the currently selected ROI.

Supervoxels are collections of voxels which are similar in terms of both data and also
spatial location. So, unlike clusters, supervoxels are always connected and localised.

For method details see https://arxiv.org/abs/1606.09518v2

The output is an ROI in which each supervoxel is an ROI region. This enables use with
for example, the mean values widget.

.. image:: screenshots/Selection_166.jpg
