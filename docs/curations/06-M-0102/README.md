# (DRAFT) The Clinical and Immunological Investigations of Subtypes of Autism

[Autism spectrum disorder (ASD)](https://medlineplus.gov/genetics/condition/autism-spectrum-disorder) is a common
neurodevelopmental disorder that is behaviorally defined, emerges early in life, encompasses a heterogeneous range of
presentations, and is characterized by deficits in social communication and patterns of restrictive/repetitive behavior.
At start of the study, Autism Spectrum Disorder was referred to as Autism disorder as defined in DSM-IV-TR. The purpose
of this study was to learn more about autism and its subtypes.

The study used comprehensive and longitudinal medical assessments, and behavioral testing to find
subgroups of children with autism with profiles that comprise distinct biological/behavioral phenotypes.

Specific goals included:

* Determining if there is a unique alteration in immune function among autistic children with a
  regressive clinical course.
* Identifying autism-specific sleep and electroenchelalogram (EEG) abnormalities.
* Identifying other potential biomarkers.

The study started on February 22, 2006, and completed on March 15, 2017.

## Participants

Participants were drawn from a longitudinal natural history study (NCT00298246) at the National Institute of Mental
Health, Bethesda, MD. A legal guardian provided written consent for participation in this NIH Combined Neurosciences
Institutional Review Board-approved study (06-M-0102).

There were 3 participant groups in this study as follows:

* **AUT**: In the autism group (AUT), autistic disorder was diagnosed using DSM-IV-TR criteria by a team of
  doctoral-level experienced clinicians, using the Autism Diagnostic Interview-Revised (ADI-R), Autism Diagnostic
  Observation Schedule (ADOS), and clinical judgement.
* **DD**: Children with significantly impaired cognitive ability but without ASD were enrolled in the non-ASD
  developmental delay (DD) group.
* **TYP**: Typically developing controls (TYP) were recruited for lack of concern in any domain of development and were
  screened using the Social Communication Questionnaire and cognitive testing.

A **total of 265 children participated in the study** and their distribution per participant group are as follows:

| Participant Group | Participant Count |
|-------------------|-------------------|
| AUT               | 140               |
| DD                | 50                |
| TYP               | 75                |

### Exclusion Criteria

* Impairing neurological disorder other than ASD that would have affected the
  validity of behavioral testing (e.g., cerebral palsy)
* Genetic abnormalities based on pathogenic findings from comparative genomic hybridization (CGH)
  microarray conducted on the ASD sample.
* If behavioral management issues (e.g. self-injury, aggressiveness) are severe to the extent that the screening
  protocol was aborted.
* Additional exclusion criteria for the TYP group included having a first‐degree relative with an ASD, a history of
  premature birth or extremely low birth weight, or history of special education services/early intervention before
  enrollment.

All scans were reviewed by a board‐certified radiologist and none were found to have clinically significant anatomical
atypicalities.

## Study Design

All children in the study were between the ages of 2 and 7.99 at baseline and were followed at 6-month or
1-year intervals. Depending on each child's study group and age, participants may undergo the following tests and
procedures:

#### Baseline Visit

* Medical and developmental history, physical examination, psychological, cognitive and medical tests to assess symptoms
  of autism or other developmental disorders, photographs of the child's face, collection of hair, urine and baby teeth
  samples. If available, hair samples from the baby's first haircut and from the biological mother's hair are also
  collected.
* **Overnight electroencephalogram (EEG):** A special cap with electrodes is placed on the child's head to measure brain
  waves (brain electrical activity) while the child sleeps in the hospital overnight.
* **Magnetic resonance imaging (MRI) scan:** The child stays in the scanner, lying still for 10 to 15 minutes at a time.
* **Lumbar puncture:** (for children in the autism) This test is done under sedation.

#### Follow-Up Visits

Follow-up visits were scheduled at different intervals, depending on study group, age and aspect of the study the child
is enrolled in. The visits include:

* A short interview session with the child's caregiver and assessment of the child's
  development and behavior.
* Some assessment measures used during the baseline examination are repeated, including
  symptoms ratings, behavioral tests and a blood test. For some children, the final visit will include repeats of the
  medical procedures. [NEED MORE CLARITY ON WHAT MEDICAL PROCEDURES]

### Neuroimaging

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

## Data Preparation Notes

Clinical assessments' data and anatomical imaging data can be accessed
as [collection 2368](https://nda.nih.gov/edit_collection.html?id=2368) on [NIMH Data Archive](https://nda.nih.gov).

Anatomical imaging data is distributed in a minimally processed, raw format. However, in order to facilitate data
analysis, the MRI data are converted to NIfTI and transformed into BIDS format using Dcm2Bids version
2.1.6 (https://github.com/UNFmontreal/Dcm2Bids/releases/tag/2.1.6), which is a wrapper for dcm2niix version
1.0.20211006 (https://github.com/rordenlab/dcm2niix).

The structural image types included in the dataset are T1w, T2w, FLAIR, PDw, and MTR. For Magnetization Transfer Ratio (
MTR) images acquired in the presence and absence of an MT pulse have the `mt-on` and `mt-off` entities in their
filenames, respectively.

To preserve subject privacy, MRI scans are defaced
using AFNI Refacer version 2.4 (https://afni.nimh.nih.gov/pub/dist/doc/htmldoc/tutorials/refacer/refacer_run.html).
Defaced scans were visually inspected for quality
using [VisualQC's](https://github.com/raamana/visualqc/tree/0.6.1https://github.com/raamana/visualqc/tree/0.6.1) suite
of QC tools. More details on the defacing workflow used can be
found [here](https://github.com/nih-fmrif/dsst-defacing-pipeline).

### Code availability

Scripts used for DICOM to BIDS format conversion and de-identification of anatomical MRI scans
are available in the git repository at https://github.com/nih-fmrif/autism-subtypes.

## Accessing Data
