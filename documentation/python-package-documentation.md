---
title: "Python Package Documentation"
excerpt: "Documentation for the clusterone Python package"
---
The Clusterone Python package makes it easy to prepare Python code to run on Clusterone. It also provides the [`just` command line interface](doc:just-cli-reference-manual) to interact with Clusterone from the command line.
[block:api-header]
{
  "title": "Installation"
}
[/block]
The clusterone package is available for [download from PyPi](https://pypi.python.org/pypi/clusterone).

The easiest way to install clusterone is using the [pip package manager](https://pypi.python.org/pypi/pip). To install the latest version with pip, open a command line and type:
```
pip install clusterone
```
[block:api-header]
{
  "title": "Import"
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Temporary Issue: Specify version number when importing!",
  "body": "Because of a temporary issue, it is necessary to specify the version number of the package to make sure your code runs on the Clusterone servers. You can do this by adding `clusterone==0.6.5` to the requirements file."
}
[/block]
Most users will only require the `get_data_path()` and `get_logs_path()` functions in their code. Import the functions into your Python code like this:
```python
from clusterone import get_data_path(), get_logs_path()
```

To use the entire clusterone package in your Python code, import it like this:
```python
import clusterone
```
[block:api-header]
{
  "title": "get_data_path()"
}
[/block]
`get_data_path()` enables your program to access data on your local machine as well as Clusterone without making changes to the code.

Returns the local dataset path if the code is run locally, or the Clusterone dataset path if the code is run on Clusterone.

### Syntax
clusterone.**get_data_path**(<i>dataset_name</i>, <i>local_root</i>, <i>local_repo</i>, <i>path</i>)

### Arguments
- `dataset_name`: _string_, Clusterone dataset path. Structure: `<owner-username>/<dataset-name>`, where `<owner-username>` is the name of the user who owns the dataset. `<dataset-name>` is the name of the dataset.
- `local_root`: _string_, root directory for the local dataset, e.g. `/home/username/datasets`
- `local_repo`: _string_, repository name inside the local root directory, e.g. `mnist`
- `path`: _string_, path inside the repository, e.g. `train`.

### Returns
- `<local_root>/<local_repo>/<path>` if the code is running on the local machine.
- `/data/<dataset_name>/<path>` if the code is running on Clusterone.

### Example
[block:code]
{
  "codes": [
    {
      "code": "from clusterone import get_data_path\n\n#...\n\ndata_path = get_data_path(\n            dataset_name = 'my_username/dataset_name',  # on ClusterOne\n            local_root = '~/Documents/datasets/',  # path to local dataset\n            local_repo = 'my_data',  # local data folder name\n            path = 'train'  # folder within the data folder\n            )",
      "language": "python"
    }
  ]
}
[/block]
In this example, `data_path` resolve to: 
- `~/Documents/datasets/my_data/train` when running the code locally 
- `/data/my_username/dataset_name/train` when running on Clusterone
[block:api-header]
{
  "title": "get_logs_path()"
}
[/block]
Returns a local log path if the code is running locally, or the log path on Clusterone if it is running on Clusterone.

### Syntax
clusterone.**get_logs_path**(<i>root</i>)

### Arguments
- `root`: _string_, local directory for logs, e.g. `/home/username/logs/mnist`

### Returns
- `<root>` if the if the code is running on the local machine.
-  `/logs/` if the code is running on Clusterone.

### Example
[block:code]
{
  "codes": [
    {
      "code": "from clusterone import get_logs_path\n\n# ...\n\nlogs_path = get_logs_path('~/Documents/tf-logs/')",
      "language": "python"
    }
  ]
}
[/block]
In this example, `logs_path` resolve to: 
- `~/Documents/tf-logs/` when running the code locally 
- `/logs/` when running on Clusterone