---
title: "Data on Clusterone"
excerpt: ""
---
Clusterone provides various different types of data storage. Regardless of their type, data storage are represented by a Dataset object on Clusterone. The following datasets are currently supported:
- **Datasets managed using Git** (either Clusterone's git or on GitHub)
- **Datasets stored on Amazon S3**
- **EFS datasets** or other NFS mounts (Clusterone Enterprise only)

We are continuously adding more data sources, please let us know on [Slack](http://slack.clusterone.com) if you want to request support for a new data source.

Regardless of the data source, a dataset has to be created on Clusterone in order to use the data when running a job. Think about a Clusterone dataset as an endpoint that a job can use to access that data.
[block:api-header]
{
  "title": "Comparison"
}
[/block]

[block:parameters]
{
  "data": {
    "h-0": "Dataset",
    "0-0": "Git",
    "1-0": "S3",
    "h-1": "Availability",
    "h-2": "Underlying storage",
    "0-1": "SaaS / Enterprise",
    "h-3": "Upload",
    "0-3": "`git push`",
    "1-3": "through third-party client",
    "2-3": "",
    "h-4": "Runtime",
    "0-4": "Data copied to local storage before job starts",
    "1-4": "Data copied to local storage before job starts",
    "2-4": "Dataset mounted on pods",
    "0-2": "GitHub or Clusterone's Git server",
    "1-1": "SaaS / Enterprise",
    "2-1": "Enterprise",
    "2-0": "EFS or other NFS mounts",
    "2-2": "AWS EFS or any NFS storage",
    "1-2": "AWS S3",
    "h-5": "Versioning",
    "0-5": "Yes",
    "1-5": "No",
    "2-5": "No"
  },
  "cols": 6,
  "rows": 3
}
[/block]
## Creating and managing datasets
The process for creating a dataset is similar for each data source, yet there are some nuances that differ depending on the source.

Check the pages dedicated to each data source for detailed instructions how to work with these sets.


## Use a dataset for running jobs
When creating a job, you can specify any number of datasets to associate to that job. At runtime, selected datasets will be mounted on `/data/<username>/<dataset-name>`. 

For example, if user `jimihendrix` has a dataset called `guitars`, at runtime this dataset will be accessible through the path `data/jimihendrix/guitars`.

Depending on the storage type, the data will be transferred to the worker's storage before job startup, or mounted.

### Running the same code locally and on Clusterone: get_data_path()
To define the path to your data, use the `get_data_path()` function from the `clusterone` Python package. It enables switching from local to a remote environment without changing your code.

For more information on `get_data_path()`, see the [documentation page](doc:python-package-documentation) for the Clusterone Python package.
[block:api-header]
{
  "title": "Sharing datasets"
}
[/block]
Datasets can be shared with other users. This allows them to use the shared dataset in their own jobs. Sharing datasets currently works with datasets hosted by Clusterone and S3 datasets. 

To share a dataset, click on it in the Matrix. Select the **Share Dataset** button on the top right. In the form, enter the username or email address of the user you want to share the dataset with. You can also add a custom message. Click the **Send** button at the bottom of the form. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9c1d63a-sharing.jpg",
        "sharing.jpg",
        653,
        117,
        "#2d2e38"
      ]
    }
  ]
}
[/block]
The dataset will now automatically appear in the invited user's list of datasets. She will also receive an email notifying her of the sharing.