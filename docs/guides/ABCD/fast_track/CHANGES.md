# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.2.0] - 2024-10-21

### Added

- Provided comprehensive lists of changes in the `code/v1.2.0/` subdirectory for this release including the lists of renamed files, added files, and scripts used to put data in place.
- Added in 2,207 new sessions (3 baseline, 203 2-year follow-up, 278 4-year follow-up, and 1,723 6-year follow-up). These were converted from DICOM data using a new DSST converter, [nimh-dsst/abcd-fasttrack2bids](https://github.com/nimh-dsst/abcd-fasttrack2bids). The full list of new sessions can be found in `code/v1.2.0/new_sessions.tsv`.

### Changed

- Replaced all existent `dwi/` folders because they had either incorrect BVAL/BVEC files from the original `DCAN-Labs/abcd-dicom2bids` conversion or they were missing some `dwi` runs.
- Removed all `fmap` sidecar `IntendedFor` fields which were empty lists.
- Updated `participants.tsv` (which is now `sessions.tsv`), `scans.tsv`, `dataset_description.json`, `CHANGES`, and `README`.

### Fixed

- Found and corrected one uncompressed NIfTI file (`*.nii`) to a compressed NIfTI file (`*.nii.gz`). The uncompressed filename can be found in `code/v1.2.0/uncompressed_nifti.tsv`.
- Found and corrected 19 corrupt NIfTI files to valid NIfTI files. The full list of corrupt files can be found in `code/v1.2.0/corrupt_niftis.tsv`.
- Recovered as many missing runs for data already on our filesystem as possible for our already-converted fast track sessions through April 2024.
- Renamed any runs that were out of order in some sessions. An inventory of renamed files can be found in `code/v1.2.0/renamed.tsv`.
- The `sessions.tsv` now only represents subjects in the `rawdata/` subfolder where it previously contained information from MRI visits as well as non-MRI visits from the annual release's tabulated data.

## [1.1.3] - 2024-02-27

### Fixed

- Corrected 1,848 MRI sessions with incorrect `task-rest` run orders. The original incorrect orders prior to this fix can be seen in `code/fast_track_run_orders_2024-02-21.json`. The corrected orders can be seen in `code/fast_track_run_orders_2024-02-27.json`. The diagnostic code and re-ordering code can be found at `code/diagnose_run_orders.py` and `code/reorder_diagnosed_runs.py`, respectively.

## [1.1.2] - 2024-02-13

### Changed

- Added two fields to `participants.tsv` and `participants.json` for the MRI `Manufacturer` and `SoftwareVersions` of converted MRI sessions.

## [1.1.1] - 2024-01-26

### Removed

- Removed subjects' rawdata, sourcedata, and derivative data for whom their consent was withdrawn as of DAIRC release 5.1. See `/data/ABCD_DSST/ABCD/consent_withdrawn.txt` for exact list of subjects.

## [1.1.0] - 2024-01-11

### Added

- Added in 1,987 new sessions (483 baseline, 485 2-year follow-up, 1,018 4-year follow-up, and 1 6-year follow-up) without DWI data (see why in the Deprecated section just below).

### Deprecated

- Found out the DWI BVAL and BVEC files are overwritten after conversion in the code we were using, so we are telling users to avoid these data for now. We are working on a fix.

## [1.0.2] - 2022-05-24

### Added

- participants.tsv and participants.json parsed and sub-selected from NDA's DAIRC ABCD Release 4.0

## [1.0.1] - 2022-05-17

### Added

- mriqc-22.0.0rc1 participant level in fast_track/derivatives/mriqc-22.0.0rc1

## [1.0.0] - 2022-05-03

### Added

- Initial DICOM download and BIDS converstion using abcd_fastqc01.txt_2021-12-21
