# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.1.3] - 2024-02-27

### Changed

- Corrected 1,848 MRI sessions with incorrect `task-rest` run orders. No problems with other `func` tasks were detected. The original incorrect orders prior to this fix can be seen in `code/fast_track_run_orders_2024-02-21.json`. The corrected orders can be seen in `code/fast_track_run_orders_2024-02-27.json`. The diagnostic code and re-ordering code can be found at `code/diagnose_run_orders.py` and `code/reorder_diagnosed_runs.py`, respectively.

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
