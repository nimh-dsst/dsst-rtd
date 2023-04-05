# Rates of cerebral protein synthesis (rCPS) in stages of sleep

## Table of Contents

1. [Introduction](#introduction)
2. [Study Overview](#study-overview)
3. [Data Overview](#data-overview)
    - [Anatomical MRI T1-weighted images](#anatomical-mri-t1-weighted-images)
    - [PET data](#pet-data)
    - [Blood sampling data](#blood-sampling-data)
    - [FreeSurfer derivative files](#freesurfer-derivative-files)
    - [rCPS statistical maps](#rcps-statistical-maps)
    - [rcps-modified-petprep group statistical maps](#rcps-modified-petprep-group-statistical-maps)
    - [rcps-modified-petprep individual derivatives](#rcps-modified-petprep-individual-derivatives)
4. [Final Notes](#final-notes)

For dataset questions or feedback, please [email Eric Earl](mailto:eric.earl@nih.gov) in the NIMH Data Science & Sharing Team.

## Introduction

The following datasets were prepared to the Brain Imaging Data Structure (BIDS) standard at the same time with the same filename and folder organizations due to their similarity:

- Effects of propofol anesthesia on rCPS
- rCPS and memory formation during sleep
- rCPS in stages of sleep
- rCPS in subjects with fragile X syndrome

Included in this dataset are L-[1-11C]leucine 4D Positron Emission Tomography (PET) images, co-registered defaced 3D anatomical Magnetic Resonanace Imaging (MRI) T1-weighted images, blood sampling data, FreeSurfer derivative files, and FreeSurfer "fsaverage" group-averaged rCPS left and right hemisphere surface statistical maps. All data were collected on the NIH campus in Bethesda, Maryland, USA. For descriptions of data acquisition and processing methods, please see the methods sections of the published papers listed in the `dataset_description.json` file.

## Study Overview

During sleep, reduced brain energy demands provide an opportunity for biosynthetic processes like protein synthesis.  Sleep is required for some forms of memory consolidation, and memory consolidation requires de novo protein synthesis.  We measured regional cerebral protein synthesis rates (rCPS) in human subjects to ascertain how brain protein synthesis is affected during sleep.  Subjects underwent three consecutive L-[1-11C]leucine PET scans with simultaneous polysomnography: 1.rested awake, 2.sleep-deprived awake, 3.sleep.  Measured rCPS were similar across the three conditions.   Variations in sleep stage times during sleep scans were used to estimate rCPS in sleep stages under the assumption that measured rCPS is the weighted sum of rCPS in each sleep stage, with weights reflecting time and availability of C-11 leucine in sleep stage.  Across regions, estimated rCPS in combined stages N1 and N2 were 7-28% higher and estimated rCPS in N3 were similar to rCPS measured in sleep-deprived awake scans. Results demonstrate increased rates of protein synthesis linked to sleep.

**Please cite**: *Picchioni, D., Schmidt, K. C., Loutaev, I., Pavletic, A. J., Sheeler, C., Bishu, S., Balkin, T. J., & Smith, C. B. (2023). Increased rates of brain protein synthesis during [N1,N2] sleep: L-[1- 11 C]leucine PET studies in human subjects. Journal of Cerebral Blood Flow & Metabolism, 43(1), 59–71. [https://doi.org/10.1177/0271678X221121873](https://doi.org/10.1177/0271678X221121873)*

## Data Overview

This dataset contains both BIDS rawdata and BIDS derivatives. The rawdata has both defaced/anonymized anatomical MRI data (in each subject's `sub-*/ses-MRI/anat` subfolder) and PET data (other sessions' `sub-*/ses-*/pet` subfolders). The derivatives dataset contains the following subfolders.

1. `derivatives/freesurfer/`: FreeSurfer recon-all derivative files
2. `derivatives/rCPS/`: Originally computed rCPS statistical maps
3. `derivatives/rcps-modified-petprep`: Modified "PETprep-matlab" (scripts made just for these data) derivative files. The code used to make these is [located here on Zenodo](https://doi.org/10.5281/zenodo.7768340).

### Anatomical MRI T1-weighted images

`sub-*/ses-MRI/anat/`

The anatomical MRI data has been converted to BIDS NIfTI using MATLAB's `niftiwrite` function, was then co-registered to the rCPS derivative images, and then defaced with [FreeSurfer's MiDeFace](https://surfer.nmr.mgh.harvard.edu/fswiki/MiDeFace) to anonymize faces. All defaced images passed a visual inspection using [Dr. Pradeep Raamana's VisualQC](https://github.com/raamana/visualqc) to ensure that no identifiable facial features were present.

### PET data

`sub-*/ses-{SESSION}/pet/*_pet.{nii.gz,json}`

The PET data are shared as-acquired after BIDS conversion. `{SESSION}` above is either `Asleep`, `Awake`, or `SleepDeprived`.

### Blood sampling data

`sub-*/ses-{SESSION}/pet/*_blood.{tsv,json}`

Blood samples were measured throughout the PET sessions. The timing and measurements are recorded in these files.

### FreeSurfer derivative files

`derivatives/freesurfer/`

The FreeSurfer recon-all derivative files are commonly provided derivatives from FreeSurfer including (but not limited to) the white matter boundary and pial boundary surfaces, cortical thickness, and cortical parcellation.

### rCPS statistical maps

`derivatives/rCPS/`

Provided by the authors, these are the original statistical maps from the paper.

### rcps-modified-petprep group statistical maps

`derivatives/rcps-modified-petprep/group/`

FreeSurfer "fsaverage" group-averaged rCPS left and right hemisphere surface maps, each with 163,842 vertices.

### rcps-modified-petprep individual derivatives

`derivatives/rcps-modified-petprep/sub-*/`

The intermediary files used produced by [`rcps-modified-petprep`](https://doi.org/10.5281/zenodo.7768340) to calculate the group-averaged rCPS surface maps.

## Final Notes

1. There is currently no BIDS standard for rCPS statistical maps. As such, their naming was inspired by [a currently unnumbered BIDS Extension Proposal, linked here](https://docs.google.com/document/d/1KHzp-yk8KXvkUIhtN71WU0m4P4kKT9C1yvI-i9_kNeY/edit?usp=sharing).

2. `sub-SP04` was removed from this dataset because they were missing both PET and MRI data.
