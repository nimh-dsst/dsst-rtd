# The Enhanced Nathan Kline Institute (NKI) - Rockland Sample

Website: http://fcon_1000.projects.nitrc.org/indi/enhanced/index.html

Neuroimaging data access instructions: http://fcon_1000.projects.nitrc.org/indi/enhanced/neurodata.html

## Download steps

   
### 1. Using python script

   1. CSV file with S3 links was downloaded from [here](http://fcon_1000.projects.nitrc.org/indi/enhanced/neurodata.html). The downloaded `aws_links.csv` file can be found at `/data/DSST/Enhanced-NKI-RS/DSST/aws_links.csv` on biowulf.
   2. Python script distributed at http://fcon_1000.projects.nitrc.org/indi/enhanced/neurodata.html was used to download
   the dataset.
      a. The following command was run from `/data/DSST/Enhanced-NKI-RS/DSST/`:
      ```bash
      swarm -f /data/DSST/Enhanced-NKI-RS/DSST/download_cmds.swarm --merge-output --job-name nki-dwnld --logdir /data/DSST/Enhanced-NKI-RS/DSST/swarm_log
      ```
      b. The above command was run three times to ensure that the files in the dataset had been downloaded completely without interruptions.
   
#### Download verification
   <details>
      <summary> Click for details </summary>

The following table shows a summary of counts based on `aws_links.csv` file (at the time of writing):
   
|                        | Counts |
|------------------------|--------|
| Rows (or S3 filepaths) | 112716 |
| **Unique** rows        | 102924 |
| Files downloaded       |  93299 |
   
By using the distributed python script for download, only 93299 files could be downloaded due to the exclusionary conditions specified in the script. The curators have been contacted to verify whether the exclusions in sessions and files is as they intended for it or if its the case that the script is outdated. (Still awaiting reply)
   
The subset of rows/files that were excluded by the python script have been stored on `/data/DSST/Enhanced-NKI-RS/DSST/aws_links_excluded_subset.csv`
</details>

   
### 2. Using AWS S3 command line tool

From a spersist session on biowulf, the following commands were run
```bash
module load aws
aws s3 cp --no-sign-request s3://fcp-indi/data/Projects/RocklandSample/RawDataBIDSLatest/ /data/NIMH_scratch/enhanced-NKI-20231026/via_s3_bucket/ --recursive
```

#### Download verification
<details>
      <summary> Click for details </summary>
Download still in progress
</details>



