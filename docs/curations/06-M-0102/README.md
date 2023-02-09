# The Clinical and Immunological Investigations of Subtypes of Autism

[Autism spectrum disorder (ASD)](https://medlineplus.gov/genetics/condition/autism-spectrum-disorder) is a common
neurodevelopmental disorder that is behaviorally defined, emerges early in life, encompasses a heterogeneous range of
presentations, and is characterized by deficits in social communication and patterns of restrictive/repetitive behavior.
The purpose of this study was to learn more about autism and its subtypes.

The study used comprehensive and longitudinal medical assessments, and behavioral testing to find
subgroups of children with autism with profiles that comprise distinct biological/behavioral phenotypes. Data collection
started on February 22, 2006, and was completed on March 15, 2017. For more information regarding the study design,
please visit [https://clinicaltrials.gov/ct2/show/NCT00298246](https://clinicaltrials.gov/ct2/show/NCT00298246).

## Neuroimaging

Given the difficulty of obtaining high-quality neuroimaging data in young children with autism, we scanned children with
autism under sedation using propofol. Sedation was performed at the NIH by board-certified anesthesiologists following a
strict clinical protocol. Typically developing controls were scanned during natural sleep at nighttime (with repeat
scans taken in the event of excess movement).

All participants were scanned on the same 1.5 T General Electric Signa scanner (Milwaukee, WI) using a
three‐dimensional (3D) spoiled gradient recalled echo sequence with the following image acquisition parameters:

| Parameter             | Value     |
|-----------------------|-----------|
| Echo time (TE)        | 5 ms      |
| Repetition time (TR)  | 24 ms     |
| Flip angle            | 45°       |
| Acquisition matrix    | 256 × 192 |
| Number of excitations | 1         |
| Field of view         | 24 cm     |

## Imaging data download

To unpack these data and satisfy the BIDS validator:

1. Download the 7 files labeled as "Results" here or download the ZIP file and unpack it.
2. Place those 7 files at the root of the BIDS folder structure.
3. Download the defaced MRI data and place the sub-* folders into the same folder structure's root level.

## Data Preparation Notes

Clinical assessments' data and anatomical imaging data can be accessed
as [collection 2368](https://nda.nih.gov/edit_collection.html?id=2368) on [NIMH Data Archive](https://nda.nih.gov). To
request access please visit [https://nda.nih.gov/nda/access-data-info.html](https://nda.nih.gov/nda/access-data-info.html).

Anatomical imaging data is shared in a minimally processed, raw format. However, in order to facilitate data
analysis, the MRI data are converted to NIfTI and transformed into BIDS format using [Dcm2Bids version
2.1.6](https://github.com/UNFmontreal/Dcm2Bids/releases/tag/2.1.6), which is a wrapper for [dcm2niix version
1.0.20211006](https://github.com/rordenlab/dcm2niix). The
following [modality agnostic files](https://bids-specification.readthedocs.io/en/stable/03-modality-agnostic-files.html#modality-agnostic-files)
have been shared as supporting documentation:

| Filename                   | Description                                                                                            |
|----------------------------|--------------------------------------------------------------------------------------------------------|
| `dataset_description.json` | A JSON file describing the dataset.                                                                    |
| `README`                   | A text file describing the dataset in greater detail.                                                  |
| `CHANGES`                  | A text file with version history of the dataset (describing changes, updates and corrections).         |
| `scans.tsv`                | A tab separated tabular file indicating the method used to deface every scan available in the dataset. |
| `scans.json`               | A JSON formatted data dictionary describing fields in `scans.tsv`.                                     |

**NOTE:** Upon downloading the imaging data from NDA, please include the above files at the root level. This is REQUIRED
if your analysis pipeline uses [BIDS Apps](https://bids-apps.neuroimaging.io/about/).

The structural image types included in the dataset are T1w, T2w, FLAIR, PDw, and MTR. For Magnetization Transfer Ratio (
MTR) images acquired in the presence and absence of an MT pulse have the `mt-on` and `mt-off` entities in their
filenames, respectively.

To preserve subject privacy, MRI scans are defaced
using [AFNI Refacer version 2.4](https://afni.nimh.nih.gov/pub/dist/doc/htmldoc/tutorials/refacer/refacer_run.html).
Defaced scans were visually inspected for quality
using [VisualQC's](https://github.com/raamana/visualqc/tree/0.6.1https://github.com/raamana/visualqc/tree/0.6.1) suite
of QC tools. 8 of the 31 scans that failed first round of QC were manually defaced
using [FSLeyes image editor](https://open.win.ox.ac.uk/pages/fsl/fsleyes/fsleyes/userdoc/editing_images.html) and the
rest were programmatically corrected to ensure defacing quality. More details on the defacing workflow used can be
found [here](https://github.com/nih-fmrif/dsst-defacing-pipeline).

**Code availability**

Scripts used for DICOM to BIDS format conversion and de-identification of anatomical MRI scans
are available on the git repository at [https://github.com/nih-fmrif/autism-subtypes](https://github.com/nih-fmrif/autism-subtypes).
