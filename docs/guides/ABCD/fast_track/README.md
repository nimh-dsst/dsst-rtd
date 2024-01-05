# ABCD Fast Track

The NDA's ABCD fast track data is released in regular batches throughout the year. We aim to keep the dataset up-to-date every 6 months or so. See [CHANGES](https://github.com/nimh-dsst/dsst-rtd/tree/main/docs/guides/ABCD/fast_track/CHANGES.md) for more info regarding the exact latest updates.

This ABCD data collection was created by downloading the NDA's fast track quality control file (abcd_fastqc01.txt), which contains Amazon S3 links to the raw DICOM imaging data for each series. Data was downloaded and converted using [a modified version of the DCAN Labs' abcd-dicom2bids code](https://github.com/nih-fmrif/abcd-dicom2bids).

## Collection contents

### sourcedata

Contains E-Prime timing files for the functional tasks.

### rawdata

Contains the unprocessed as-converted imaging data

### derivatives

Available current derivatives include:

- `mriqc-22.0.0rc1`

## Quality Control information

Data in this collection includes all data, regardless of the quality rating provided from the ABCD DAIRC. The QC file that was used to download and convert the data is in the `code/abcd_fastqc01_history/` subdirectory.

You can find a summarized version of the QC ratings in our aggregated file `code/qc.tsv`. This QC file includes the ratings made by the ABCD DAIRC from the NDA's `abcd_fastqc01.txt` file as well as mappings from the NDA's `ftq_series_id` to the BIDS tree filenames. You can find the full data dictionary at `code/qc.json`.

- Note 1: No field map's QC ratings are included in this `ABCD_BIDS.abcd_fastqc01.txt` file because they could not be directly mapped from NIfTI names to exact `ftq_series_id` from the original spreadsheet.
- Note 2: No DWI image's QC ratings are currently included because of the known issue with the current DWI BVAL ancd BVEC files outlined in the "known issues" below.

## Known issues

1. The `dwi` BVAL and BVEC files are not currently usable. The BVAL and BVEC files were overwritten after conversion in the code we were using, so we are encouraging users to avoid these data for now. We are working on a fix.
1. 471 sessions are still undergoing conversion attempts. They will be included if/when they are successfully converted.
1. For a subset of subjects with only a single direction of `dwi` field maps, there is an error in the `IntendedFor` field of the `.json` sidecar file. This is currently being investigated, if you wish to use these please contact Dustin ([dmoracze@nih.gov](mailto:dmoracze@nih.gov)) or Eric ([eric.earl@nih.gov](mailto:eric.earl@nih.gov)) for a status update on fixing this issue.
