# ABCD Fast Track

The NDA's ABCD fast track data is released in regular batches throughout the year. We aim to keep the dataset up-to-date every 6 months or so. See CHANGES for more info regarding the exact latest updates.

This ABCD data collection was created by downloading the NDA's fast track quality control file (abcd_fastqc01.txt), which contains Amazon S3 links to the raw DICOM imaging data per series. Data was downloaded and converted using [a modified version of the DCAN Labs' abcd-dicom2bids code](https://github.com/nih-fmrif/abcd-dicom2bids).

## Collection contents

### sourcedata

eprime timing files for the functional tasks

### rawdata

Unprocessed converted imaging data

### derivatives

Current derivatives include:

- mriqc-22.0.0rc1

## Quality Control information

Data in this collection includes all data, regardless of the quality rating provided from the ABCD DAIRC. The QC TSV that was used to download and convert the data is in the `code/abcd_fastqc01_history` subdirectory.

You can find the DAIRC's QC ratings of each image in `code/fast_track.abcd_fastqc01_current.txt`, see the columns `ftq_usable` for the QC ratings and `related` for the corresponding image. Note: No field map's QC ratings are included in this `ABCD_BIDS.abcd_fastqc01.txt` file because they could not be directly mapped from NIfTI names to exact `ftq_series_id` from the original spreadsheet.

## Known issues

For a subset of subjects with only a single direction of `dwi` field maps, there is an error in the `IntendedFor` field of the `.json` sidecar file. This is currently being investigated, if you wish to use these please contact Dustin ([dmoracze@nih.gov](mailto:dmoracze@nih.gov)) or Eric ([eric.earl@nih.gov](mailto:eric.earl@nih.gov)) for a status update on fixing this issue.
