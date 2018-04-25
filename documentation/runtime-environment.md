---
title: Runtime Environment
excerpt: The environment available at runtime
---

# Runtime Environment

Each job on Clusterone runs in its own separate container. The mount points for code and data are always the same, independent of the type of project and the data source.

At runtime, the following folders are available to each job:

* `/data` contains datasets
* `/code` contains code
* `/logs` contains outputs that will be saved after termination

  \[block:api-header\]

  {

  "title": "Data"

  }

  \[/block\]

  When creating a job, you can select datasets that should be available for this job. They will be mounted in the `/data` folder and can be accessed there through your project code.

Each dataset is mounted in its own folder. The folder structure is as follows: `/data/<owner-username>/<dataset-name>`.

* `<owner-username>` is the username of the owner of the dataset. If you created the dataset, this is your username. If another user has shared a dataset with you, this is the username of the user who owns the dataset.
* `<dataset-name>` is the name of the dataset. This is the name you gave the dataset when you created it.

## Mounting characteristics by dataset source

\[block:parameters\] { "data": { "h-0": "Data source", "h-1": "Mount type", "h-2": "Impact of changes at runtime", "0-0": "Clusterone Git", "0-1": "Copied before runtime", "0-2": "No effect on original dataset \(unless `git push`\)", "1-0": "GitHub", "1-1": "Copied before runtime", "1-2": "No effect on original dataset\n\(unless `git push`\)", "2-0": "Amazon S3", "2-1": "Copied before runtime", "2-2": "No effect on original dataset", "3-0": "Amazon EFS \(Clusterone Enterprise only\)", "3-1": "Mounted directly on pod", "3-2": "Original dataset is modified" }, "cols": 3, "rows": 4 } \[/block\] As can be seen in the table above, Git and S3 datasets are copied before runtime. Changes to their content will not impact the original dataset. EFS datasets, on the other hand, are mounted on the pods. Changes to their content directly affect the source.

## The get\_data\_path\(\) function

The Clusterone Python package offers the `get_data_path()` convenience function to make simplify switching between local execution of a script and running it on Clusterone.

The function automatically detects if a project is run on a local machine or on Clusterone and returns the correct path to the dataset accordingly. It accepts the path to the local file and the owner name and dataset name on Clusterone as inputs.

See the [Python Package Documentation](doc:python-package-documentation) for more details on `get_data_path()`. \[block:api-header\] { "title": "Projects" } \[/block\] The code of the project associated with the job is copied to `/code/<username>/<project-name>` when a job is created. \[block:api-header\] { "title": "Log files" } \[/block\] All outputs are stored in `/logs`. These files will persist after the job terminates and are available from the [Matrix](https://clusterone.com/matrix) as outputs.

Clusterone's integrated TensorBoard also reads summaries from the `/log` folder of a job. \[block:api-header\] { "title": "Environment variables" } \[/block\]

\[block:parameters\] { "data": { "h-0": "Variable", "h-1": "Content", "0-0": "TF\_CONFIG", "0-1": "For distributed TensorFlow, the cluster definition and the mapping of IP:PORT that each pod can access. See [more details](https://www.tensorflow.org/api_docs/python/tf/train/ClusterSpec)" }, "cols": 2, "rows": 1 } \[/block\]

