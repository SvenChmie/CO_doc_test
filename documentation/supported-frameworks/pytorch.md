---
title: "PyTorch"
excerpt: ""
---
## From the Matrix
Select PyTorch at the _Environment_ step of the job creation wizard. Only the latest version of PyTorch is supported.

## From the command line
Use `just create job` with the following option:  `--framework pytorch-1.0.0`
[block:code]
{
  "codes": [
    {
      "code": "just create job single --project <project> --datasets <dataset> \\\n--framework pytorch-1.0.0",
      "language": "shell",
      "name": "create pytorch job"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "danger",
  "title": "Requirements",
  "body": "If you are using PyTorch as a framework, do _not_ specify pytorch or torchvision in the requirements file as it will cause an error. Use `--framework pytorch-1.0.0` or select PyTorch through the matrix instead."
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Distributed Training",
  "body": "Distributed training is not currently supported in PyTorch"
}
[/block]
## PyTorch and TensorBoard
It is possible to take advantage of TensorBoard even in PyTorch! [This repository](https://github.com/lanpa/tensorboard-pytorch) provides a TensorBoard API for PyTorch (or any other framework).
Include the following in the requirements:
[block:code]
{
  "codes": [
    {
      "code": "tensorboardX",
      "language": "shell",
      "name": "pip - requirements.txt"
    },
    {
      "code": "name: clusterone\ndependencies:\n  - tensorboardX",
      "language": "yaml",
      "name": "conda - requirements.yml"
    }
  ]
}
[/block]
Then use the following snippet:
[block:code]
{
  "codes": [
    {
      "code": "...# you requirements\nfrom tensorboardX import SummaryWriter\nfrom clusterone import get_logs_path\nimport os\n\n#Your local path to outputs, locally tensorboard summaries will be saved here\nROOT_PATH_TO_LOCAL_LOGS = os.path.expanduser(\"~/Documents/pytorch-projects/examples/logs\")\n\n... #model definition\n\nif __name__ == \"__main__\":\n  writer = SummaryWriter(log_dir = get_logs_path(ROOT_PATH_TO_LOCAL_LOGS))\n  \n  for batch_index in range(nb_batches):\n    ... # training operation\n    loss = ... # compute your loss\n    #only save loss to tensorboard every n batches to not slow down training\n    \n    if batch_index % 100 == 0: \n      writer.add_scalar('loss', loss, batch_index)\n\n\n\n",
      "language": "python",
      "name": "tensorboard_pytorch"
    }
  ]
}
[/block]
See [basic examples](https://github.com/malomarrec/pytorch-examples).
See the full [tensorboard-pytorch API documentation](https://github.com/lanpa/tensorboard-pytorch).