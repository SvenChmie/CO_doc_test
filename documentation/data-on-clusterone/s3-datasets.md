---
title: "S3 Datasets"
excerpt: ""
---
You can use Amazon S3 to store datasets and natively import them when running jobs on Clusterone. An [Amazon S3](https://aws.amazon.com/s3/) user login ([IAM](https://aws.amazon.com/iam/)) is automatically created when signing up for Clusterone. 

S3 datasets on Clusterone correspond to S3 buckets on AWS. Each user can create any number of datasets.

This page provides an overview of how to create a dataset on S3. See [here](doc:data-on-clusterone) for an overview of other available options for storing datasets.
[block:api-header]
{
  "title": "Create an S3 dataset"
}
[/block]
When creating a new S3 dataset, a new bucket is created in S3. Additionally, a new dataset is created in your Clusterone account. This dataset represents the S3 bucket in Clusterone and you can use it just like any other type of dataset.

Please note that the name you choose for your dataset and thus the S3 bucket needs to be **unique throughout all of AWS**. Make sure the name is personal and reflects the data that your set contains.

### From the CLI

To create a new S3 dataset, run:
``` bash
just create dataset s3 <dataset-name>
```
Note that the dataset name needs to be unique across AWS. The command will return an error in case the name is already taken.

### From the Matrix
In the dataset view, click the **Add Dataset** button. On the first page of the wizard, select **S3** as data source.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/daa30e0-Add_Dataset_S3.JPG",
        "Add_Dataset_S3.JPG",
        1645,
        509,
        "#28404a"
      ]
    }
  ]
}
[/block]
On the next wizard page, choose a name for your dataset. Note that each dataset has to have a unique name across AWS.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4cbf2d1-Add_Dataset_S3_Step2.JPG",
        "Add_Dataset_S3_Step2.JPG",
        1646,
        844,
        "#26353f"
      ]
    }
  ]
}
[/block]
Click **Add Dataset**. A new bucket is created in the S3 account that is connected to your Clusterone account.
[block:api-header]
{
  "title": "Add data to an S3 dataset"
}
[/block]
You can add and modify your S3 dataset directly through Amazon Web Services. 

Please note that the listing of available buckets is disabled for security reasons. When connecting with a client, you will have to specify the bucket you want to access.

### Using the AWS CLI
We recommend using the [AWS CLI](https://aws.amazon.com/cli/) for uploading data to an S3 dataset. Other clients, such as 3Hub, often suffer from much lower uploading speeds.

To upload data to an S3 bucket with the AWS CLI, follow these steps:
1. Install the AWS CLI
2. Run `aws configure` and input your access key and secret key. [See here](doc:s3-account) to learn where to find these keys in your Clusterone account.
3. Run `aws s3 cp <source-file> s3://<bucket-name>` for file upload or `aws s3 cp <source-folder> s3://<bucket-name> --recursive` for folder upload.
[block:api-header]
{
  "title": "Create a job with an S3 dataset"
}
[/block]
Creating a job that uses an S3 dataset works the same way as for any other type of dataset. 

When using the job creation wizard in the Matrix, simply select the S3 dataset you want to use with the job.

Using the CLI, specify the name of your S3 dataset with the `--datasets` argument.
[block:api-header]
{
  "title": "At Runtime"
}
[/block]
When running a job, data will be copied from S3 to Clusterone's distributed storage to enable maximum speed when running the job. The job will start once the download is complete. Billing will start _after_ the data is copied and the job has started.

The content of an s3 dataset named `<username>/<dataset-name>` will be available at runtime in `/data/<username>/<dataset-name>`.

After the job terminates, data will _not_ persist on the pods, so the changes made to the data will not be saved.
[block:api-header]
{
  "title": "Performance"
}
[/block]
Downloading from an S3 storage can be slow. In particular, downloading a large collection of small files can slow down the transfer speed. For large S3 datasets, we recommend having a few large files rather than small files.

*Clusterone Enterprise offers a variety of storage options. Get in touch via Intercom, and our solutions team will help you finding the option that is best for you.*