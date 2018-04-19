---
title: "Datasets hosted by Clusterone"
excerpt: ""
---
When creating a new dataset, you have the option to store the data in a Git repository on the Clusterone servers.

See [here](doc:data-on-clusterone) for an overview of other available options.
[block:api-header]
{
  "title": "Create dataset"
}
[/block]
### In the Matrix
Toggle the switch on the left side to show your datasets. Click on the **Add Dataset** button in the center.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/14e8434-Add_Dataset_Button.JPG",
        "Add_Dataset_Button.JPG",
        1242,
        237,
        "#2d3540"
      ]
    }
  ]
}
[/block]
In the wizard, select **Create internal Git repository**. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/32fdd45-Add_Dataset_Step_1_CO.JPG",
        "Add_Dataset_Step_1_CO.JPG",
        1646,
        505,
        "#274049"
      ]
    }
  ]
}
[/block]
On the next page, specify a dataset name. Optionally, you can add a description and choose tags. This is useful if you have many different datasets that you want to group together.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9bc465d-Add_Dataset_Step_2_CO.JPG",
        "Add_Dataset_Step_2_CO.JPG",
        1645,
        806,
        "#263741"
      ]
    }
  ]
}
[/block]
In the last step, click **Add Dataset**. Success, you just created a new dataset on Clusterone!

### In the CLI

Creating a new dataset on Clusterone with the CLI is as easy as: 
``` bash
$ just create dataset <dataset-name>
```

The path to your dataset will be `username/dataset-name`.

[block:api-header]
{
  "title": "Prepare data"
}
[/block]
To add data to your Clusterone dataset, you need to store the data in a Git repository. Additionally, you may want to install [Git LFS](https://git-lfs.github.com/), a software that Clusterone uses to handle large data files.

If your dataset is not in a Git repository yet, create a new Git repository:
``` bash
$ git init
```

If your dataset contains large files, Git LFS is a useful tool to deal with these large files. For example, if you have .h5 files in your data, track them like this: 
``` bash
$ git lfs track *.h5
```

Next, add and commit the changes: 
``` bash
$ git add -A
$ git commit -m "added dataset"
```
[block:api-header]
{
  "title": "Link a local repository"
}
[/block]
To make sure Git knows where to push the data to, you need to link your local Git repository to your Clusterone dataset:
``` bash
$ just ln dataset -p <dataset-name>
```

This adds Clusterone as a remote origin to your dataset.
See the [CLI Reference Manual](doc:just-cli-reference-manual) for more information on the [`just ln`](doc:just-ln) command.
[block:api-header]
{
  "title": "Push commits"
}
[/block]
Once your local Git repository is linked to Clusterone, all you need to do to push it is this:
``` bash
git push clusterone master
```
[block:api-header]
{
  "title": "Clone a repository"
}
[/block]
If you want to download your Clusterone dataset, you can use Git's clone command to do so.

Open the Matrix and navigate to the dataset you want to clone. Click the **Settings** tab. Find the Git URL and copy it to your clipboard. It should look similar to this: `https://git.clusterone.com/username/datasetname.git`.

Now head over to your command line and run (make sure to replace `<Git-URL>` with the URL you just copied):
``` bash
git clone <Git-URL>
```

To be able to push commits from this repository back to the Clusterone dataset, don't forget to link the repository.