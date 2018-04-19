---
title: "TensorFlow"
excerpt: ""
---
Clusterone supports a variety of different versions of TensorFlow, including the most recent releases.  Below we outline how you can choose TensorFlow when creating jobs through the [Matrix](https://clusterone.com/matrix), as well as the command line. 
[block:api-header]
{
  "title": "From the Matrix"
}
[/block]
In the _Environment_ step of the job creation wizard, select TensorFlow as the framework. On the right, select the TensorFlow version you want to use.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9a32f95-Create_Job_TF_Version.JPG",
        "Create_Job_TF_Version.JPG",
        1350,
        893,
        "#26323c"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "From the command line"
}
[/block]
Use `just create job distributed` or `just create job single` with the following options:
 `--framework tensorflow-<version>`
 where version can be either `1.0.0`, `1.2.0`, `1.3.0`, `1.4.0`, or `1.5.0`

Example:
[block:code]
{
  "codes": [
    {
      "code": "just create job distributed --project <project> --datasets <dataset> \\\n--framework tensorflow-1.0.0",
      "language": "shell",
      "name": "create tensorflow job"
    }
  ]
}
[/block]