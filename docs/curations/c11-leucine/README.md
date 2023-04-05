# Measurements of rCPS in human subjects

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

### Effects of propofol anesthesia on rates of cerebral protein synthesis (rCPS)

The purpose of this study was to determine the effects of 2,3-diisopropylphenol (propofol) anesthesia on rCPS. We studied 10 healthy young male volunteers who each underwent two L-[1-11C]leucine PET studies: awake and anesthetized with propofol. Our measurements showed no significant effects of propofol anesthesia on values of rCPS in all examined regions.

**Please cite**: *Bishu, S., Schmidt, K. C., Burlin, T. V., Charming, M. A., Horowitz, L., Huang, T., Liu, Z., Qin, M., Vuong, B.-K., Unterman, A. J., Xia, Z., Zametkin, A., Herscovitch, P., Quezado, Z., & Smith, C. B. (2009). Propofol Anesthesia Does Not Alter Regional Rates of Cerebral Protein Synthesis Measured with l -[1- 11 C]Leucine and PET in Healthy Male Subjects. Journal of Cerebral Blood Flow & Metabolism, 29(5), 1035–1047. [https://doi.org/10.1038/jcbfm.2009.7](https://doi.org/10.1038/jcbfm.2009.7)*

### Rates of cerebral protein synthesis (rCPS) and memory formation during sleep

If protein synthesis during sleep is required for sleep-dependent memory consolidation, we might expect rates of cerebral protein synthesis (rCPS) to increase during sleep in the local brain circuits that support performance on a particular task following training on that task. In this study, in order to measure circuit-specific brain protein synthesis during a daytime nap opportunity, we used the L-[1-11C]leucine positron emission tomography (PET) method with simultaneous polysomnography. We trained subjects on the visual texture discrimination task (TDT). This was followed by a nap opportunity during the PET scan, and we retested them later in the day after the scan. The TDT is considered retinotopically specific, so we hypothesized that higher rCPS in primary visual cortex would be observed in the trained hemisphere compared to the untrained hemisphere in subjects who were randomized to a sleep condition. Our results indicate that the changes in rCPS in primary visual cortex depended on whether subjects were in the wakefulness or sleep condition but were independent of the side of the visual field trained. That is, only in the subjects randomized to sleep, rCPS in the right primary visual cortex was higher than the left regardless of side trained. Other brain regions examined were not so affected. In the subjects who slept, performance on the TDT improved similarly regardless of the side trained. Results indicate a regionally selective and sleep-dependent effect that occurs with improved performance on the TDT.

**Please cite**: *Picchioni, D., Schmidt, K. C., McWhirter, K. K., Loutaev, I., Pavletic, A. J., Speer, A. M., Zametkin, A. J., Miao, N., Bishu, S., Turetsky, K. M., Morrow, A. S., Nadel, J. L., Evans, B. C., Vesselinovitch, D. M., Sheeler, C. A., Balkin, T. J., & Smith, C. B. (2018). Rates of cerebral protein synthesis in primary visual cortex during sleep-dependent memory consolidation, a study in human subjects. Sleep, 41(7). [https://doi.org/10.1093/sleep/zsy088](https://doi.org/10.1093/sleep/zsy088)*

### Rates of cerebral protein synthesis (rCPS) in stages of sleep

During sleep, reduced brain energy demands provide an opportunity for biosynthetic processes like protein synthesis.  Sleep is required for some forms of memory consolidation, and memory consolidation requires de novo protein synthesis.  We measured regional cerebral protein synthesis rates (rCPS) in human subjects to ascertain how brain protein synthesis is affected during sleep.  Subjects underwent three consecutive L-[1-11C]leucine PET scans with simultaneous polysomnography: 1.rested awake, 2.sleep-deprived awake, 3.sleep.  Measured rCPS were similar across the three conditions.   Variations in sleep stage times during sleep scans were used to estimate rCPS in sleep stages under the assumption that measured rCPS is the weighted sum of rCPS in each sleep stage, with weights reflecting time and availability of C-11 leucine in sleep stage.  Across regions, estimated rCPS in combined stages N1 and N2 were 7-28% higher and estimated rCPS in N3 were similar to rCPS measured in sleep-deprived awake scans. Results demonstrate increased rates of protein synthesis linked to sleep.

**Please cite**: *Picchioni, D., Schmidt, K. C., Loutaev, I., Pavletic, A. J., Sheeler, C., Bishu, S., Balkin, T. J., & Smith, C. B. (2023). Increased rates of brain protein synthesis during [N1,N2] sleep: L-[1- 11 C]leucine PET studies in human subjects. Journal of Cerebral Blood Flow & Metabolism, 43(1), 59–71. [https://doi.org/10.1177/0271678X221121873](https://doi.org/10.1177/0271678X221121873)*

### Rates of cerebral protein synthesis (rCPS) in subjects with fragile X syndrome

Fragile X syndrome (FXS) is the most common inherited cause of intellectual disability.  Fragile X mental retardation protein, a putative translation suppressor, is significantly reduced in FXS.   The prevailing hypothesis is that rCPS are increased by the absence of this regulatory protein. We have previously reported increased rCPS in the Fmr1 knockout mouse model of FXS.  To address the hypothesis in human subjects, we applied the L [1-11C]leucine PET method to measure rCPS in adults with FXS  and healthy controls.  

#### Studies in conscious subjects

In previous studies we had used sedation during imaging (References 1 and 2) and we did not find increases in rCPS as had been seen in the mouse model.  Since mouse measurements were conducted in awake animals, we considered the possibility that sedation may have confounded our results.  In this study (Reference 3) we used a modified and validated PET protocol that made it easier for participants with FXS to undergo the study awake. We compared rCPS in 10 fragile X participants and 16 healthy controls all studied while awake.  Contrary to the prevailing hypothesis and findings in Fmr1 knockout mice, results indicate that rCPS in awake participants with FXS are decreased in whole brain and most brain regions by 13-21% compared to healthy controls.

#### Studies in subjects under dexmedetomidine anesthesia

In this study (Reference 2) all subjects were males between the ages of 18 and 24 years and free of psychotropic medication.  As most fragile X participants were not able to undergo the PET study awake, we used dexmedetomidine for sedation during the imaging studies.  We found no differences between rCPS measured during dexmedetomidine-sedation and the awake state in ten healthy controls.  In the comparison of rCPS in dexmedetomidine-sedated fragile X participants (n=9) and healthy controls (n=14) we found no statistically significant differences.  These results in human subjects do not support the findings in animal models that rCPS are elevated in the absence of FMRP.  

**Please cite**:

1. *Bishu, S., Schmidt, K. C., Burlin, T. V., Charming, M. A., Horowitz, L., Huang, T., Liu, Z., Qin, M., Vuong, B.-K., Unterman, A. J., Xia, Z., Zametkin, A., Herscovitch, P., Quezado, Z., & Smith, C. B. (2009). Propofol Anesthesia Does Not Alter Regional Rates of Cerebral Protein Synthesis Measured with l -[1- 11 C]Leucine and PET in Healthy Male Subjects. Journal of Cerebral Blood Flow & Metabolism, 29(5), 1035–1047. [https://doi.org/10.1038/jcbfm.2009.7](https://doi.org/10.1038/jcbfm.2009.7)*

2. *Schmidt, K. C., Loutaev, I., Quezado, Z., Sheeler, C., & Smith, C. B. (2020). Regional rates of brain protein synthesis are unaltered in dexmedetomidine sedated young men with fragile X syndrome: A L-[1-11C]leucine PET study. Neurobiology of Disease, 143, 104978. [https://doi.org/10.1016/j.nbd.2020.104978](https://doi.org/10.1016/j.nbd.2020.104978)*

3. *Schmidt, K. C., Loutaev, I., Burlin, T. V., Thurm, A., Sheeler, C., & Smith, C. B. (2022). Decreased rates of cerebral protein synthesis in conscious young adults with fragile X syndrome demonstrated by L-[1- 11 C]leucine PET. Journal of Cerebral Blood Flow & Metabolism, 42(9), 1666–1675. [https://doi.org/10.1177/0271678X221090997](https://doi.org/10.1177/0271678X221090997)*

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

The PET data are shared as-acquired after BIDS conversion. `{SESSION}` above is either **FILLINTHEBLANK**.

#### `fragile_x`

1. `Awake`
2. `Dex`

#### `propofol_anesthesia`

1. `Awake`
2. `Propofol`

#### `sleep_memory`

1. `Asleep`
2. `Awake`

#### `sleep_stages`

1. `Asleep`
2. `Awake`
3. `SleepDeprived`

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

2. `sub-HM20` was removed from the Fragile X study and `sub-SP04` from the sleep stages study because they were missing both PET and MRI data.
