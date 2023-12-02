# Associations between neighborhood resources and youth's response to reward omission in a task modeling negatively biased environments

A comprehensive dataset characterizing a transdiagnostic sample of youth ages 8 to 18 years using clinical assessments, structural magnetic resonance imaging (MRI), functional MRI and behavioral data acquired during the Affective Posner (AP) task, and Child Opportunity Index (COI 2.0) scores.

## Data Source

Data were collected at the National Institute of Mental Health (NIMH), Bethesda, Maryland by the [Emotion and Development Branch (EDB)](https://www.nimh.nih.gov/research/research-conducted-at-nimh/research-areas/clinics-and-labs/edb). 

## Licensing

This dataset is licensed under the [Creative Commons Zero (CC0) v1.0 License](https://creativecommons.org/publicdomain/zero/1.0/).

## Participant Eligibility and Characteristics

### Inclusion Criteria

Participants were aged 8 to 18 years and spoke English. Additionally, participants in the study met the following inclusion criteria:
  
* Met the criteria for attention-deficit/hyperactivity disorder (ADHD) as assessed with the KSADS  
* Met the criteria for an anxiety disorder(s) (ANX) as assessed with the KSADS  
* Met the criteria for disruptive mood dysregulation disorder (DMDD) as assessed with the KSADS  
* Did NOT meet the criteria for any psychiatric disorder (i.e., healthy volunteer, HV) as assessed with the KSADS  

### Exclusion Criteria

Participants meeting any of the criteria listed below were excluded from the study:  

* Full-scale IQ < 70
* Neurological disorders  
* Pervasive developmental disorders  (e.g., autism spectrum disorder)
* Unstable and/or chronic medical illness
* Psychosis  
* Bipolar disorders 
* Conduct disorder
* Suicidal ideation 
* Substance use
* MRI contraindications (e.g., claustrophobia, pregnancy)  
* Any medical condition that increases risk for complications during MRI (e.g., pacemaker, metallic foreign body in eye, dental braces)
* Additional exclusion criteria for ANX patients were: (e.g., current Tourette’s syndrome, obsessive-compulsive disorder, major depressive disorder, post-traumatic stress disorder, and current psychotropic medication use).

### Consent

Institutional Review Board approval, parent or guardian consent, and child assent were obtained. To characterize the sample, we collected data on participants' race/ethnicity, parental income, and use of psychotropic medication. 

## Clinical Measures

### Completed by Participants : 
* [Affective Reactivity Index (youth-ARI)](https://doi.org/10.1111%2Fj.1469-7610.2012.02561.x)
* [Screen for Child Anxiety Related Disorders (SCARED-Child)](https://doi.org/10.1097/00004583-199704000-00018)
* [Children's Depression Inventory (CDI)](https://psycnet.apa.org/doi/10.1037/t19482-000)
* [Wechsler Abbreviated Scale of Intelligence (WASI)](https://psycnet.apa.org/doi/10.1037/t15170-000)

### Completed by Participants' parents/caregivers: 
* [Affective Reactivity Index (parent-ARI)](https://doi.org/10.1111%2Fj.1469-7610.2012.02561.x) 
* [Screen for Child Anxiety Related Disorders (SCARED-Parent)](https://doi.org/10.1097/00004583-199704000-00018)
* [Conners Comprehensive Behavioral Rating Scale (CBRS)](https://doi.org/10.1007/978-0-387-79948-3_1534)

### Completed by Clinicians: 
* [Kiddie Schedule for Affective Disorders (KSADS)](https://doi.org/10.1097/00004583-199707000-00021)

## Study Group
Participants were recruited in the context of two ongoing studies and completed two versions of the AP task. These two cohorts are drawn from subsamples of two published studies. Cohort 1 corresponds to [Tseng et al., 2019 (doi:10.1176/appi.ajp.2018.18040491)](https://doi.org/10.1176/appi.ajp.2018.18040491), while Cohort 2 corresponds to [Linke et al., 2023 (doi:10.1016/j.jaac.2022.11.009)](https://doi.org/10.1016/j.jaac.2022.11.009). Membership in each cohort is signified in the `cohort` column of `participants.tsv`. In this dataset, there are 119 participants from Cohort 1 and 42 participants from Cohort 2.

## Child Opportunity Index (COI 2.0) 
The [Child Opportunity Index 2.0](https://www.diversitydatakids.org/sites/default/files/2020-02/ddk_coi2.0_technical_documentation_20200212.pdf) measures neighborhood resources and conditions and allows to compare the level of opportunity that neighborhoods provide for children across the U.S. COI 2.0 includes 29 indicators that measure neighborhood-based opportunities for children including but not limited to access and quality of early childhood education (ECE), high-quality schools, green space, healthy food, toxin-free environments, socioeconomic resources and more. The 29 indicators are grouped into three domains: education, health and environment, and social and economic. Data were retrieved based on the street addresses provided by the participants. We used the national rank score for our analysis but provide also the scores normed at the state and metro levels. 

## Imaging Protocol

### Affective Posner (AP) Task

Previous publications provide details of AP task version [1 (doi:10.1176/appi.ajp.2018.18040491)](https://doi.org/10.1176/appi.ajp.2018.18040491) and [2 (doi:10.1016/j.jaac.2022.11.009)](https://doi.org/10.1016/j.jaac.2022.11.009). There are several differences between the two versions:

* Version 1: all 4 runs were acquired in the scanner
* Version 2: only runs 3 and 4 were acquired in the scanner

### T2*-weighted images (Blood-Oxygen-Level Dependent (BOLD) contrast)

All T2*-weighted images were acquired with the following parameters: TR = 2.3 s, voxel size = 2.5 x 2.5 x 3.0 mm, matrix size = 96 x 96.

For a subset of participants (across 476 runs), there were 206 TRs and the associated images include `acq-206timepoints` in the filename. For the remaining participants (across 84 runs), there were 179 TRs and the associated images include `acq-179timepoints` in the filename.

There are also several other differences in scan parameters, including:
* Echo time (TE) and effective echo spacing
* Number of interleaved axial slices
* Flip angle
* Version of `dcm2niix` used

### T1-weighted Scans

For 119 participants, T1-weighted images were acquired with 0.86 x 0.86 x 1.20 mm non-isotropic voxels and the associated images include `acq-noniso` in the filename. For the remaining 42 participants, T1-weighted images were acquired with 1.00 mm isotropic voxels and the associated images include `acq-iso` in the filename.

There are also several other differences in scan parameters, including:
* Repetition time (TR)
* Echo time (TE)
* Matrix size
* Flip angle
* Version of `dcm2niix` used

## Description of Data Formats and Preparation

### Clinical Measures Data

Clinical measures can be found in the `phenotype.tsv` file, with each measure/assessment described in the `phenotype.json` file. The `n/a` values indicate that the question may have been skipped over by the participant or not presented to/asked of the participant.

### Imaging Data

Imaging data in this study is distributed in NifTI format after undergoing conversion from DCM via `dcm2niix`. The images were acquired with a 3.0 Tesla field strength.

We have de-identified the anatomical scans by defacing the scans using v1.0.0 of the [DSST Defacing Pipeline](https://github.com/nimh-dsst/dsst-defacing-pipeline/).

### AP Task Data Acquisition & Organization

For Cohort 1, all four runs of the AP task were acquired in the scanner, and trial-level information for each run can be found in the `events.tsv` files in the `func/` directories.

For Cohort 2, the first two runs were acquired without fMRI data and trial-level information for these runs can be found in the `beh.tsv` files in the `beh/` directories. The third and fourth task runs for Cohort 2 were acquired with fMRI data, and trial-level information for these runs can be found in the `events.tsv` files in the `func/` directories.

The `duration` column in each `events.tsv` file refers to the duration of the cue, target, and response period for all `cue` events and the duration of the feedback screen for all `feedback` events.

The AP task behavioral data (i.e., response time and accuracy) are currently missing for two participants:
* `s23837` is missing behavioral data for all 4 runs. The `beh.tsv` files are empty for runs 1 and 2, and the `events.tsv` files for runs 3 and 4 do not include any information besides the onset, duration, trial, and event.
* `s24198` is missing behavioral data for run 2 only. The `beh.tsv` file is empty for run 2.

## Citing This Dataset

If you use this dataset in your research, please consider citing the original studies:

* [Tseng et al., 2019 (doi:10.1176/appi.ajp.2018.18040491)](https://doi.org/10.1176/appi.ajp.2018.18040491)
* [Linke et al., 2023 (doi:10.1016/j.jaac.2022.11.009)](https://doi.org/10.1016/j.jaac.2022.11.009)
