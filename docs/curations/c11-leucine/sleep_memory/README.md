# Rates of cerebral protein synthesis (rCPS) and memory formation during sleep

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

If protein synthesis during sleep is required for sleep-dependent memory consolidation, we might expect rates of cerebral protein synthesis (rCPS) to increase during sleep in the local brain circuits that support performance on a particular task following training on that task. In this study, in order to measure circuit-specific brain protein synthesis during a daytime nap opportunity, we used the L-[1-11C]leucine positron emission tomography (PET) method with simultaneous polysomnography. We trained subjects on the visual texture discrimination task (TDT). This was followed by a nap opportunity during the PET scan, and we retested them later in the day after the scan. The TDT is considered retinotopically specific, so we hypothesized that higher rCPS in primary visual cortex would be observed in the trained hemisphere compared to the untrained hemisphere in subjects who were randomized to a sleep condition. Our results indicate that the changes in rCPS in primary visual cortex depended on whether subjects were in the wakefulness or sleep condition but were independent of the side of the visual field trained. That is, only in the subjects randomized to sleep, rCPS in the right primary visual cortex was higher than the left regardless of side trained. Other brain regions examined were not so affected. In the subjects who slept, performance on the TDT improved similarly regardless of the side trained. Results indicate a regionally selective and sleep-dependent effect that occurs with improved performance on the TDT.

**Please cite**: *Picchioni, D., Schmidt, K. C., McWhirter, K. K., Loutaev, I., Pavletic, A. J., Speer, A. M., Zametkin, A. J., Miao, N., Bishu, S., Turetsky, K. M., Morrow, A. S., Nadel, J. L., Evans, B. C., Vesselinovitch, D. M., Sheeler, C. A., Balkin, T. J., & Smith, C. B. (2018). Rates of cerebral protein synthesis in primary visual cortex during sleep-dependent memory consolidation, a study in human subjects. Sleep, 41(7). [https://doi.org/10.1093/sleep/zsy088](https://doi.org/10.1093/sleep/zsy088)*

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

The PET data are shared as-acquired after BIDS conversion. `{SESSION}` above is either `Asleep` or `Awake`.

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

There is currently no BIDS standard for rCPS statistical maps. As such, their naming was inspired by [a currently unnumbered BIDS Extension Proposal, linked here](https://docs.google.com/document/d/1KHzp-yk8KXvkUIhtN71WU0m4P4kKT9C1yvI-i9_kNeY/edit?usp=sharing).
