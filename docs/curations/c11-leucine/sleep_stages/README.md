# Rates of cerebral protein synthesis (rCPS) in stages of sleep

For dataset questions or feedback, please email the NIMH Data Science & Sharing Team at [nimhdsst@mail.nih.gov](mailto:nimhdsst@mail.nih.gov).

## Introduction

Included in this dataset are L-[1-11C]leucine 4D Positron Emission Tomography (PET) images, co-registered defaced 3D anatomical Magnetic Resonanace Imaging (MRI) T1-weighted images, blood sampling data, FreeSurfer derivative files, and FreeSurfer "fsaverage" group-averaged rCPS left and right hemisphere surface statistical maps. All data were collected on the NIH campus in Bethesda, Maryland, USA. For descriptions of data acquisition and processing methods, please see the methods sections of the published papers listed in the `dataset_description.json` file.

## Study Overview

During sleep, reduced brain energy demands provide an opportunity for biosynthetic processes like protein synthesis. Sleep is required for some forms of memory consolidation, and memory consolidation requires de novo protein synthesis. We measured regional cerebral protein synthesis rates (rCPS) in human subjects to ascertain how brain protein synthesis is affected during sleep.<sup>1</sup> Subjects underwent three consecutive L-[1-11C]leucine PET scans with simultaneous polysomnography: 1.rested awake, 2.sleep-deprived awake, 3.sleep. Measured rCPS were similar across the three conditions. Variations in sleep stage times during sleep scans were used to estimate rCPS in sleep stages under the assumption that measured rCPS is the weighted sum of rCPS in each sleep stage, with weights reflecting time and availability of C-11 leucine in sleep stage. Across regions, estimated rCPS in combined stages N1 and N2 were 7-28% higher and estimated rCPS in N3 were similar to rCPS measured in sleep-deprived awake scans. Results demonstrate increased rates of protein synthesis linked to sleep.

### Please cite the following paper when using this dataset

1. *Picchioni, D., Schmidt, K. C., Loutaev, I., Pavletic, A. J., Sheeler, C., Bishu, S., Balkin, T. J., & Smith, C. B. (2023). Increased rates of brain protein synthesis during [N1,N2] sleep: L-[1- 11 C]leucine PET studies in human subjects. Journal of Cerebral Blood Flow & Metabolism, 43(1), 59–71. [https://doi.org/10.1177/0271678X221121873](https://doi.org/10.1177/0271678X221121873)*

## Data Overview

This dataset contains both BIDS rawdata and BIDS derivatives. The rawdata is composed of:

1. `sub-*/ses-MRI/anat/*_T1w.{nii.gz,json}`: Defaced/anonymized anatomical MRI T1-weighted images
    - These T1-weighted images were converted to BIDS NIfTI using MATLAB's `niftiwrite` function, then co-registered to the rCPS derivative images, and then defaced with [FreeSurfer's MiDeFace](https://surfer.nmr.mgh.harvard.edu/fswiki/MiDeFace) to anonymize faces. All defaced images passed a visual inspection using [Dr. Pradeep Raamana's VisualQC](https://github.com/raamana/visualqc) to ensure that no identifiable facial features were present.
2. `sub-*/ses-{SESSION}/pet/*_pet.{nii.gz,json}`: PET data
    - The PET data are shared as-acquired after BIDS conversion. `{SESSION}` above is either `Asleep`, `Awake`, or `SleepDeprived`.
3. `sub-*/ses-{SESSION}/pet/*_blood.{tsv,json}`: Blood sampling data
    - Blood samples were measured throughout the PET sessions. The timing and measurements are recorded in these files.

The derivatives dataset is composed of:

1. `derivatives/freesurfer/`: FreeSurfer recon-all derivative files
    - The FreeSurfer recon-all derivative files are commonly provided derivatives from FreeSurfer including (but not limited to) the white matter boundary and pial boundary surfaces, cortical thickness, and cortical parcellation.
2. `derivatives/rCPS/`: Originally computed rCPS statistical maps
    - Provided by the authors, these are the original statistical maps from the paper.
3. `derivatives/rcps-modified-petprep/sub-*/`: Modified "PETprep-matlab" (scripts made just for these data) derivative files. The code used to make these is [located here on Zenodo](https://doi.org/10.5281/zenodo.7768340).
    - The intermediary files used produced by [`rcps-modified-petprep`](https://doi.org/10.5281/zenodo.7768340) to calculate the group-averaged rCPS surface maps.
4. `derivatives/rcps-modified-petprep/group/`: Modified "PETprep-matlab" (scripts made just for these data) group-averaged statistical maps.
    - FreeSurfer "fsaverage" group-averaged rCPS left and right hemisphere surface maps, each with 163,842 vertices.

## Notes

1. The following datasets were prepared to the Brain Imaging Data Structure (BIDS) standard at the same time with the same filename and folder organizations due to their similarity:

    - Effects of propofol anesthesia on rCPS
    - rCPS and memory formation during sleep
    - rCPS in stages of sleep
    - rCPS in subjects with fragile X syndrome

2. There is currently no BIDS standard for rCPS statistical maps. As such, their naming was inspired by [a currently unnumbered BIDS Extension Proposal, linked here](https://docs.google.com/document/d/1KHzp-yk8KXvkUIhtN71WU0m4P4kKT9C1yvI-i9_kNeY/edit?usp=sharing).

3. `sub-SP04` was removed from this dataset because they were missing both PET and MRI data.
