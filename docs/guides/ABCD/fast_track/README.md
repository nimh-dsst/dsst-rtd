# ABCD Fast Track

The NDA's ABCD fast track data is released in regular batches throughout the year. We aim to keep the dataset up-to-date every 6 months or so. See [CHANGES](https://github.com/nimh-dsst/dsst-rtd/tree/main/docs/guides/ABCD/fast_track/CHANGES.md) for more info regarding the exact latest updates.

This ABCD data collection was created by downloading the NDA's fast track quality control file (abcd_fastqc01.txt), which contains Amazon S3 links to the raw DICOM imaging data for each series. Data was downloaded and converted originally using [a modified version of the DCAN Labs' abcd-dicom2bids code](https://github.com/nih-fmrif/abcd-dicom2bids). The data was updated in v1.2.0 with a new DSST converter, [nimh-dsst/abcd-fasttrack2bids](https://github.com/nimh-dsst/abcd-fasttrack2bids), in order to get complete, correct, and consistent data.

All subjects who withdrew their consent have been removed from all `rawdata`, `sourcedata`, and `derivatives` folders.

## Collection contents

### derivatives

Contains processed derivatives of rawdata under folders named after their pipeline name and pipeline software version like: `<pipeline>-<version>/`.

### rawdata

Contains the unprocessed as-converted imaging data which was not recalled (see "Quality Control information" below for more on what "not recalled" means).

### sourcedata

Contains E-Prime timing files for the functional tasks.

## Quality Control (QC) information

Data in this collection includes all non-recalled data (`ftq_recalled` = 0), regardless of the quality rating (`ftq_usable`) provided from the ABCD Data Analysis Informatics & Resource Center (DAIRC). See Note 1 below for more on `ftq_usable`. The QC file that was used to download and convert the data is in the `code/abcd_fastqc01_history/` subdirectory.

You can find a summarized version of the QC ratings in our aggregated file `scans.tsv`. This file includes the QC ratings made by the ABCD DAIRC from the NDA's `abcd_fastqc01.txt` file as well as mappings from the NDA's `ftq_series_id` to the BIDS tree filenames. You can find the full data dictionary in `scans.json`.

- **Note**: The `ftq_usable` field is a summary measure indicating that the series is not missing any DICOMs (`ftq_complete` = 1), passed "raw" QC and has no severe artifacts (`ftq_quality` = 1), and has not been recalled by consent being withdrawn or NDA file replacement (`ftq_recalled` = 0).

## Known issues

1. 139 `3YearFollowUpYArm1` sessions are still undergoing conversion. They will be included after they are successfully converted to BIDS. They include a few new data types like HERMES, QSM, and SWI.
1. There is a very small sample of as-yet-unconverted series that need to be checked individually before inclusion for accuracy, due to DAIRC `abcd_fastqc01.txt` file-naming issues.
1. There are 10 sessions whose DWI data are missing due to conversion problems.
1. There are 7 new sessions missing due to their series having conversion problems.

## Field map (`fmap`) `IntendedFor` fields

The `IntendedFor` fields in the `acq-func` JSON sidecar files are currently assigned by using the DCAN Labs' eta-squared method of selecting the best spin-echo field map pair among all spin-echo field map pairs in a session to be used to distortion-correct all fMRI runs within that session.
