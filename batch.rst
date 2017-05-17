Batch processing
================

Often it is useful to be able to run a set of analysis / processing steps on a whole set of files, without
needing to manually load and save the files separately within the GUI. Quantiphyse provides a simple batch 
processing system which gives access to most of the processing steps available from the GUI.

Batch files are written in YAML syntax. Below is a simple example.

::

    # Example config file for running Fabber

    OutputFolder: out
    Debug: True
    SaveVolume:
    SaveOverlays:
        mean_c0 :
        mean_c1:
        mean_c2:
    SaveRois:
        mask:

    Processing:
        - Fabber:
            method: vb
            max-iterations: 30
            model:  poly
            noise: white
            degree: 2 
            save-mean:

    Cases:
        Subj0001:
            Folder:   c:\mydata\0001
            Volume:   mri.nii
            Rois:
                mask:   roi.nii
        Subj0003:
            Folder:   c:\mydata\0003
            Volume:   mri.nii
            Rois:
                mask:   roi.nii
        Subj0003:
            Folder:   c:\mydata\0003
            Volume:   mri.nii
            Rois:
                mask:   roi.nii

The batch file is divided into three main sections. First we have statements to set up default options which
will apply to all cases. In this example we are putting all output data in the ``out`` folder, enabling Debug
messages, and specifying what data we want to save for each case - in this case we are going to save the original
main data volume, three overlays which will be produced by the ``Fabber`` process, and the ROI.

The next section defines a series of processing steps. Here we have only one - running the Fabber modelling
tool. Options to provide to the tool are given here.

Finally, we have a list of ``Cases``. The processing steps will be run separately on each case and saved in separate 
subdirectories of the output folder.

Output
------

The output from processing is stored in ``OutputFolder`` in a subdirectory named by the case identifier 
(e.g. ``Subj0001``). Each processing step also generates a log file (e.g. ``Fabber.log``) in the same
subdirectory. In the above example we would expect the following output structure:

::

    out/Subj0001/mri.nii
    out/Subj0001/mean_c0.nii
    out/Subj0001/mean_c1.nii
    out/Subj0001/mean_c2.nii
    out/Subj0001/mask.nii
    out/Subj0001/Fabber.log
    out/Subj0002/mri.nii
    out/Subj0002/mean_c0.nii
    out/Subj0002/mean_c1.nii
    out/Subj0002/mean_c2.nii
    out/Subj0002/mask.nii
    out/Subj0002/Fabber.log
    out/Subj0003/mri.nii
    out/Subj0003/mean_c0.nii
    out/Subj0003/mean_c1.nii
    out/Subj0003/mean_c2.nii
    out/Subj0003/mask.nii
    out/Subj0003/Fabber.log

Overriding processing options within a case
-------------------------------------------

If a particular case needs options to be varied, you can override any of the toplevel options within the case block.
For example.

::

    Cases:
        Subj0001:
            Folder:   c:\mydata\0001
            Volume:   mri.nii
            Rois:
                mask:   roi.nii
            # This case does not converge in 30 iterations
            Fabber:
                max-iterations: 100

Or, if one case is causing problems we might enable debug mode just for that case

::

    Debug: False

    Cases:
        Subj0005:
            Folder:   c:\mydata\0005
            Volume:   mri.nii
            Rois:
                mask:   roi.nii
            # What's going on here?
            Debug: True

Multiple processing steps
-------------------------

The ``Processing`` block contains a list of steps, which will be performed in order. For example this
example performs motion correction on the main data, followed by PK modelling:

::

    Processing:
        - Moco:
            method: deeds
            replace-vol: True
            ref-vol: 14
        - PkModelling:
            model:      1
            fa:         30     # degrees
            tr:         5.0    # ms
            te:         2.2    # ms
            dt:         0.5    # temporal resolution (s)
            r1:         3.7    # T1 Relaxivity of contrast agent
            r2:         4.8    # T2 Relaxivity of contrast agent
            ve-thresh:  99.8   # Ktrans/kep percentile threshold
            tinj:       60     # Approximate injection time (s) 

Artifacts
---------

*Artifacts* are data created by processing modules which are not voxel data, but can be saved to a text
file. They can be saved in the same way as data using the ``SaveArtifacts`` command. For example
the ``CalcVolumes`` process calculates the volume of each region of an ROI and outputs a table 
artifact.

::

    OutputFolder: out

    Processing:
    - CalcVolumes:
            output-name: roi_vols

    SaveArtifacts:
        roi_vols:

    Cases:
        Subject1:
            Folder:   c:\Users\ctsu0221\build\data
            Volume:   test_data.nii
            Rois:
            mask:   test_mask.nii

In this case, the volume data will be saved in ``out/Subject1/roi_vols.txt``. In this case the
output is a tab-separated file which can be loaded into a spreadsheet.
