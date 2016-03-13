# PkView 

(build 0.2)

Viewer for 3D and 4D functional data and Pharmacokinetic modelling

**Please acknowledge this software in any publication or other work that uses analysis, results or figures generated by this software**

**Disclaimer:
This software has been developed for research purposes only, and should not be 
used as a diagnostic tool. The authors or distributors will not be responsible for 
any direct, indirect, special, incidental, or consequential damages arising of the use of this software.**

The current intention of this software is for "in house" use only and shouldn't be distributed without the explicit consent of the authors. 


## Installation

Executables are available for Ubuntu, Windows and OSx. 


## Basic Usage

#### Load 4D volume

PKView loads images, rois and overlays from nifti files. 

Either: 

1) Drag and drop a 4D nifti file onto the viewer

or

2) File -> Load Image

![Image 1](screenshots/1.png)

When dragging and dropping, a window will pop up to specify whether the image is a 4D volume, ROI or overlay. 

![Image 2](screenshots/2.jpg)

The image will appear in the 3 views. 
Options
- Zoom using the **right mouse button**
- **Left mouse button** click a point
- **scroll** using the mouse wheel
- Options allow scaling based on the voxel size

![Image 1](screenshots/3.png)

#### Load ROI and overlays

Drag-and-drop or load overlays in a similar way.

For overlays specify the overlay type or a generic type (as show below)

![Image 1](screenshots/4.jpg)

Switch between loaded or generated overlays from the *current overlays* section of the **Volumes** widget. 

![Image 1](screenshots/5.png)


## Voxel analysis widget

- The voxel analysis widget gives the enhancement curve of the currently selected location. 

![Image 1](screenshots/6.png)

- Multiple points can be selected with multiple colors
- These points only appear on the axial slice and need to be cleared before changing clear. 
- Points can be cleared with X


![Image 1](screenshots/7.png)


## Overlay options widget

- Transparency, color map and overlay threshold can be changed in the **Overlay options**. 
- Overlay statistics can also be calculated for each ROI label in the *Overlay Statistics* section. 

![Image 1](screenshots/9.png)


## Curve clustering widget

- PCA based curve clustering allows clustering of tumour subregions based on contrast enhancement characteristics. 
- Number of clusters
- PCA modes used for clustering
- Advanced options: Merge clusters, get cluster sizes

![Image 1](screenshots/10.png)


## Overlay clustering widget

- Cluster based on a particular ROI map
- Step 1: Select the overlay of interest

![Image 1](screenshots/13.png)

- Step 2: Cluster based on the selected ROI. 
- Get slice and volume statistics

![Image 1](screenshots/12.png)



## PK modelling widget

![Image 1](screenshots/15.png)


## Visualisation of model fit widget

![Image 1](screenshots/14.png)

Images copyright 2016 Benjamin Irving
