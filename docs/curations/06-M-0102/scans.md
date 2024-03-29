# `scans.json`

```json
{
  "filename": {
    "Description": "Relative paths to '.nii.gz' files."
  },
  "participant_id": {
    "Description": "A participant identifier of the form sub-<label>, matching a participant entity found in the dataset."
  },
  "session_id": {
    "Description": "A session identifier of the form ses-<label>, matching a session entity found in the dataset."
  },
  "suffix": {
    "Description": "Type of anatomical scan. All scans in the dataset are in NIfTI format.",
    "Levels": {
      "T1w": "A T1-weighted image.",
      "T2w": "A T2-weighted image.",
      "PDw": "Proton density (PD) weighted image.",
      "FLAIR": "Fluid attenuated inversion recovery image.",
      "mt-on_MTR": "A Magnetization Transfer Ratio image with magnetization state (MTState) set to on.",
      "mt-off_MTR": "A Magnetization Transfer Ratio image with magnetization state (MTState) set to off."
    }
  },
  "defacing_type": {
    "Description": "Method of defacing applied to the scan.",
    "Levels": {
      "direct": "AFNI's @afni_refacer_run defacing program was run on the scan to produce a defaced scan and it's defacemask.",
      "aligned": "Scan registered to 'primary_scan' within session with FSL FLIRT. Defacemask, produced by running @afni_refacer_run on 'primary_scan' within session, used to mask out facial features.",
      "manual": "To ensure systematic editing of brain volume, the steps are described as follows: 1. Create a binary mask of the original image. 2. Overlay the binary mask on the original image. 3. Change the opacity of the overlay to 50%. 4. Select kernel size of five. 5. Switch to 3D mode. 6. Change the voxel values of the overlaid binary mask to zero if it contains facial features such as chin, nose, and eyes. 7. Save the modified binary mask. 8. Apply modified mask to the original scan to create a defaced image.",
      "none": "If the acquired image did not have any facial features, then it was shared as is."
    }
  }
}
```
