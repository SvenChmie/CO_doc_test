---
title: "Job Output"
excerpt: ""
---
A running job produces two types of output: 
- data output, stored in a virtual directory at `/data`.
- log files

Both types of data can be downloaded or viewed in the Matrix, as well as downloaded using the CLI.
[block:api-header]
{
  "title": "Download files with the CLI"
}
[/block]
Use the `download_files` command to download all output data files of a completed job. It takes the local destination path as a positional argument. The job ID of the job you'd like to download is passed using the `--job-id` argument:
``` bash
just download_files /local/destination/ --job-id <job-ID>
```
[block:api-header]
{
  "title": "View and download files in the Matrix"
}
[/block]
Find the job you'd like to see the output for in your job list. Click on **See Details** below the job name and select the **Outputs** tab in the menu bar. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/11afb08-Job_Outputs.jpg",
        "Job_Outputs.jpg",
        1873,
        737,
        "#2e3543"
      ]
    }
  ]
}
[/block]
This page shows a list of output files that have been produced by the job. You can click on the file name to open a preview in the browser. Note that this only works with text-based files.

On the right side of each file is a **Download** button. Click it to download a copy of the output file.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/49def33-Job_Outputs_2.jpg",
        "Job_Outputs_2.jpg",
        1200,
        627,
        "#323647"
      ]
    }
  ]
}
[/block]