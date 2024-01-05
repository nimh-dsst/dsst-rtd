# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- Added in 1,987 new sessions (483 baseline, 485 2-year follow-up, 1,018 4-year follow-up, and 1 6-year follow-up) without DWI data (see why in the Deprecated section just below).

### Deprecated

- Found out the DWI BVAL and BVEC files are overwritten after conversion in the code we were using, so we are encouraging users to avoid these data for now. We are working on a fix.

## [1.0.2] - 2022-05-24

### Added

- participants.tsv and participants.json parsed and sub-selected from NDA's DAIRC ABCD Release 4.0

## [1.0.1] - 2022-05-17

### Added

- mriqc-22.0.0rc1 participant level in fast_track/derivatives/mriqc-22.0.0rc1

## [1.0.0] - 2022-05-03

### Added

- Initial DICOM download and BIDS converstion using abcd_fastqc01.txt_2021-12-21
