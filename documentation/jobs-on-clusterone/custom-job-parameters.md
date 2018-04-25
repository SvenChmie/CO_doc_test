---
title: Custom Job Parameters
excerpt: ''
---

# Custom Job Parameters

When creating a job, you can pass command line arguments to the Python module that is executed. These parameters can be evaluated in Python like regular command line arguments.

This can be useful to test different configurations of a model without having to change the code. Different configurations of the same model can even be run concurrently in separate jobs. \[block:api-header\] { "title": "Passing custom arguments to a job" } \[/block\] Custom arguments can be passed to the Python module that is executed when a job runs. This has to be done when the job is created. Once created, a job is immutable and no arguments can be passed or changed.

The arguments are passed to the job when creating it using the `just create job` command of the CLI. Simply specify your custom arguments along with the argument of the create command in the format `--<name> <value>`. Note that custom arguments cannot have the same name as regular arguments of the job creation command.

[See here](doc:just-create-job) for more information about the `just create job` command. \[block:api-header\] { "title": "Evaluating arguments in Python" } \[/block\] Custom arguments are passed to the Python file the same way arguments are passed when running `python my-python-file --arg value`. They can be evaluated with Python's [argparse](https://docs.python.org/3.5/library/argparse.html) module or similar modules.

