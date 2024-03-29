# Pre-processing pipeline

## Table of contents

- [Pre-processing pipeline](#pre-processing-pipeline)
  - [Table of contents](#table-of-contents)
  - [The data](#the-data)
  - [Conversion to NIFTI](#conversion-to-nifti)
  - [Onset files](#onset-files)
  - [More info](#more-info)
    - [1. Localizers](#1-localizers)
    - [2. Structural MRI](#2-structural-mri)
    - [3. Functional MRI](#3-functional-mri)
    - [4. Distorsion fields](#4-distorsion-fields)
  
## The data

Description of the experiment.

## Conversion to NIFTI

The standard output of a MRI scanner (Magnetic resonance imaging) is DICOM, although it sometimes can be found as NIFTI.

The first thing you will need to do is to convert the DICOM files that look like this:

``` bash
MR.1.3.12.2.1107.5.2.43.167017.2017121412583114227636143
MR.1.3.12.2.1107.5.2.43.167017.2017121412583131155436146
MR.1.3.12.2.1107.5.2.43.167017.2017121412583148080636149
MR.1.3.12.2.1107.5.2.43.167017.2017121412583165051536152
MR.1.3.12.2.1107.5.2.43.167017.2017121412583181919336155
MR.1.3.12.2.1107.5.2.43.167017.2017121412583198848836158
```

into NIFTI data. To do so, can run this command in any bash terminal.
First, write in a terminal:

`sudo apt-get install dcm2niix`

Then, run the next command. Be sure to add the path where you want the data to be written. If you want more information about the command, be sure to check out the help command or go to their webpage [here](https://github.com/rordenlab/dcm2niix).

`dcm2nii -o $PATH_FOR_OUTPUT $PATH_DICOM_FILES`

The type of files you can find after the conversion could be: [localizers](#1-localizers), [structural MRI](#2-structural-mri), [functional MRI](#3-functional-mri) or [distorsion fields](#4-distorsion-fields).

As an output, you will get something similar to:

``` bash
20171214_120713BOLDMOSAIC12815mmisos007a001.nii.gz
20171214_120713BOLDMOSAIC12815mms003a001.nii.gz
20171214_120713BOLDMOSAIC12815mms004a001.nii.gz
20171214_120713DistortionMapAPs005a1001.nii.gz
20171214_120713DistortionMapPAs006a1001.nii.gz
20171214_120713localizers001a1001A.nii.gz
20171214_120713localizers001a1001B.nii.gz
20171214_120713localizers001a1001.nii.gz
20171214_120713MPRAGEADNIiPAT2s002a1001.nii.gz
co20171214_120713MPRAGEADNIiPAT2s002a1001.nii.gz
o20171214_120713MPRAGEADNIiPAT2s002a1001.nii.gz
```

For now, the files that matter to us are the structural scan (`20171214_120713MPRAGEADNIiPAT2s002a1001.nii.gz`), the functional files (`20171214_120713BOLDMOSAIC12815mms003a001.nii.gz` and `20171214_120713BOLDMOSAIC12815mms004a001.nii.gz`) and the distorsion maps(`20171214_120713DistortionMapAPs005a1001.nii.gz` and `20171214_120713DistortionMapPAs006a1001.nii.gz`.

## Onset files

*These files are only needed in a task-based fMRI.*

Onset files are necessary to specify what stimulus was played at what time. Every software requires them to be in a specific way. In the case of **_FSL_**, you must have one file per stimulus.

## More info

### 1. Localizers

Explanation

### 2. Structural MRI

Explanation

### 3. Functional MRI

Explanation

### 4. Distorsion fields

Explanation

End.
