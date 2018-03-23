Registration and Motion Correction
==================================

*Widgets -> Processing -> Registration*

This widget enables registration and motion correction using various methods. Currently implemented methods 
are:

 - DEEDS - a nonlinear fully deformable registration method
 - MCFLIRT - a linear affine/rigid body registration method

Not all methods may be included in all builds.

In Registration mode you must select the data to register and the reference data. The reference data
must be a static volume, if multi-volume data is selected you have to choose which volume to use. The
options are:

 - Middle volume, i.e. if there are 5 volumes, use the third.
 - Mean volume, i.e. take the mean of all volumes in the series and use that
 - Specified volume, allowing the user to choose which volume to use. Note that the first volume is numbered 0.

The registration data can be single or multi-volume. If it is multi-volume, each volume is registered to the 
reference data.

Motion correction is implemented as self-registration. Multi-volume data is selected and each volume is 
registered to a specific volume within the same series, or the mean of the series. The options for this are 
as listed above.

The registered data can be saved under a specified name, or can be set to replace the original data.

Each registration method has its own set of options which are available when it is selected.
