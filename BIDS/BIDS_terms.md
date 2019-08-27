# BIDS keywords <!-- omit in toc -->

## The basic structure <!-- omit in toc -->



## The DICOM to BIDS converter (see [here(https://github.com/cbedetti/Dcm2Bids)]) <!-- omit in toc -->

An example of the configuration file for the converter [Dcm2Bids](https://github.com/cbedetti/Dcm2Bids) (converts your DICOMS into a BIDS data structure with NIFTIs inside through [dcm2niix](https://github.com/rordenlab/dcm2niix)):

``` JSON
{
    "searchMethod": "fnmatch",
    "defaceTpl": "pydeface --outfile {dstFile} {srcFile}",
    "descriptions": [
        {
            "dataType": "anat",
            "modalityLabel": "T1w",
            "criteria": {
                "SeriesDescription": "*T1W_3D*"
            }
        },
                {
            "dataType": "anat",
            "modalityLabel": "T2w",
            "criteria": {
                "SidecarFilename": "007*",
                "EchoTime": 0.1
            }
        },
        {
            "dataType": "func",
            "modalityLabel": "bold",
            "customLabels": "task-rest",
            "criteria": {
                "SeriesDescription": "rs_fMRI"
            },
            "sidecarChanges": {
                "SeriesDescription": "rsfMRI"
            }
        },
        {
            "dataType": "fmap",
            "modalityLabel": "fmap",
            "criteria": {
                "SidecarFilename": "*echo-4*"
            },
            "IntendedFor": 5 ## Number of the subject that the deface is intended for.
        }
    ]
}
```

To be able to fill the configuration file for the Dcm2Bids code, it is essential to know the right words to use in each of their categories. Here you will find a glossary of the most used keywords in BIDS. They will be divided by the category so you will find:

- [dataType](#datatype)
- [modalityLabel](#modalitylabel)
- [customLabels](#customlabels)
- [criteria](#criteria)
  - [SeriesDescription](#seriesdescription)
  - [SidecarFilename](#sidecarfilename)
- [Non-BIDS acquisitions](#non-bids-acquisitions)

All of these keywords were obtained from the official BIDS website. If you want to add more info to each of your description, you may go to [**there**](https://bids-specification.readthedocs.io/en/stable/) and find their description.


## dataType

Data type is a functional group of different types of data. In BIDS there are these data types:

| Keyword    | Description
|  :---:     | -
|`anat`      | Any MRI anatomical scan would be defined by this label. Even if they have any of these formats: T1w, T2w, T1rho, T1map, T2map, T2star, FLAIR, FLASH, PD, PDmap, PDT2, inplaneT1, inplaneT2,angio. Deface masks are also defined with this keyword.
|`func`      | Imaging data acquired during functional imaging (i.e. imaging which supports rapid temporal repetition). This includes but is not limited to task based fMRI as well as resting state fMRI (i.e. rest is treated as another task). For task based fMRI a corresponding task events file MUST be provided (please note that this file is not necessary for resting state scans). For multiband acquisitions, one MAY also save the single-band reference image as type sbref.
|`dwi`       | Any diffusion-weighted imaging data.

|`fmap`      | Data acquired to correct for B0 inhomogeneities. Also known as distorsion maps, fieldmaps or deformation fields.

|`beh`       | Any results from behavioral experiments performed along imaging data acquisitions, as well as experiments performed outside of the scanner.

|`meg`       | Any magnetoencephalography data acquired on the same subject.

|`eeg`       | Any EEG data.

|`ieeg`      |

|`channels`  |

|`headshape` |

|`markers`   |

|`photo`     |

|`electrodes`|

|`events`    |

|`ignorebids`|



















## modalityLabel


## customLabels


## criteria


### SeriesDescription


### SidecarFilename


## Non-BIDS acquisitions
As found [here](https://docs.flywheel.io/hc/en-us/articles/360017426934-How-do-I-name-scan-acquisitions-so-they-can-be-in-BIDS-format-in-Flywheel-), not all acquisitions that are acquired during a session are relevant to the BIDS standard. One example would be localizer scans. The BIDS Gear will set an ignore flag on that file if it's labeled with a known non-BIDS classification, like Localizer. However, if another acquisition may not be BIDS relevant but might otherwise look like a BIDS data type, the user should include the string:

``` json
            ignore-bids
```

in their acquisition label.
