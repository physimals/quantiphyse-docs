ROI Builder
===========

- *Widgets -> ROI Builder*

This widget is designed for simple construction of regions of interest and manual segmentation. It is not 
designed to be a replacement for sophisticated semi-automatic segmentation tools!

Basic concept
-------------

At the top of the widget, you can choose the name of the ROI you are building. You can also select the 
ID of the region you are currently constructing - ROIs can have multiple region IDs, for example to 
identify two distinct tumours.

Below these options is the toolbox. Each tool allows you to modify the ROI region - typically on a single slice
of the image. Generally with manual segmentation, you work slice by slice, drawing around the region as you go.
If you are doing this, you may want to maximise one of the viewing windows first. The ``Crosshairs`` tool
allows you to interact with the viewing images in the normal way, without starting to draw ROI shapes on them.

Another use of the ROI tool is for quick definition of simple ROIs for testing. For example you 
could define a small region of a few voxels to test a long-running analysis procedure before running it on the 
full image. In this case, defining a region on a single slice may be sufficient.

Tools
-----

Rectangle
~~~~~~~~~

Simple click-and-drag to select a rectangular region. When you are happy, click ``Add`` to add it to the ROI, or 
click ``Discard`` to ignore it.

Ellipse
~~~~~~~

Identical to the ``Rectangle`` tool, but selects an elliptical region

Polygon
~~~~~~~

In this tool, each click on the image adds a vertex of a polygon region. When you click ``Add`` the last node is
connected to the first node to close the polygon, and the interior is selected.

Eraser
~~~~~~

With this tool, you click on individual voxels to remove them from the ROI

Pen
~~~

This is a typical tool for manual segmentation. Click and drag to draw a boundary around the region you want to
select. Clicking ``Add`` adds the interior of the region to the ROI.








