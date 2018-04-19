---
title: "anaconda"
excerpt: ""
---
To use pip as a package manager, you need to define your requirements in a `requirements.yml` file and add it to your Project on Clusterone ([anaconda documentation](https://conda.io/docs/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file))
For example:
[block:code]
{
  "codes": [
    {
      "code": "name: clusterone\nchannels:\n  - soumith\ndependencies:\n  - pytorch\n  - torchvision\n  - cuda80",
      "language": "yaml",
      "name": "requirements.yml"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "danger",
  "title": "The environment name in the yaml file has to be `clusterone`."
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Local check",
  "body": "You can check locally that this file is valid by running: `conda env create -f requirements.yml`"
}
[/block]
After this file has been added to your project code, you will need to specify it when running a job.
[block:api-header]
{
  "title": "From the GUI"
}
[/block]
At the Environment step, select conda as the package manager. `requirements.yml` is the default name for the requirements file, update it as needed.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b76c0d9-job-wizard-conda.png",
        "job-wizard-conda.png",
        1974,
        1272,
        "#252737"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "From the CLI"
}
[/block]
Use `just run` with the 
`package-manager conda --requirements requirements.yml` option.

` --requirements` defaults to ` requirements.yml` and is optional.