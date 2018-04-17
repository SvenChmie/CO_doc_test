---
title: "Create a Dataset"
excerpt: ""
---
Clusterone stores datasets separate from the project code. For the MNIST demo, you don't need to upload a dataset, we've already taken care of that for you. 

But what if you want to use your own dataset? No problem!

On Clusterone, datasets are stored in a Git repository separate from your project code. To be able to handle large datasets, Clusterone uses Git LFS.

If you don't have Git LFS yet, go get it [here](https://git-lfs.github.com/).
[block:api-header]
{
  "title": "Prepare your dataset for Clusterone"
}
[/block]
Navigate your command line to the folder containing your dataset.

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
This operation can take a moment if the data is large.
[block:api-header]
{
  "title": "Create the dataset on Clusterone"
}
[/block]
Create a new dataset on Clusterone with: 
``` bash
$ just create dataset MyFavoriteDataset
```
Link your local Git repository to the dataset:
``` bash
$ just ln dataset -p MyFavoriteDataset
```

The last step is pushing the dataset to Clusterone.
``` bash
$ git push clusterone master
```
The path to your dataset will be `username/dataset-name`.

The transfer might take a while, so go get yourself a nice coffee, or use the time to read some of the great articles on our [blog](http://medium.com/clusterone)!