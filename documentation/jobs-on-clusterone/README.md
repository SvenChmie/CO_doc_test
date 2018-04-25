---
title: Jobs on Clusterone
excerpt: ''
---

# Jobs on Clusterone

Executing code on Clusterone happens in **jobs**. A job represents the configuration of the environment that the code runs it. This configuration includes which code file to run, what data to operate on, and so forth. See below for a list of available job parameters.

A job can be run many times, each time creating the exact same runtime configuration. To run the code with a different configuration, you have to create a new job.

After a job has finished its execution, the output data from the run is available. If the code supports it, a job can also be analyzed in TensorBoard.

See here\(doc:job-output\) to learn more about data output from a job. \[block:api-header\] { "title": "Job Parameters" } \[/block\] When creating a job, you can configure a variety of parameters. This section discusses the parameters and their impact on the job execution.

To learn more about how to create and run jobs, see [here](doc:run-a-job). You might also want to take a look at the [reference manual](doc:just-create-job) of the Clusterone CLI.

## Project and Code Paths

* Project: This is the repository where the code job should run is stored in. See [here](doc:code-on-clusterone) to learn more about projects on Clusterone.
* Git commit: All repository options are based on Git. You can choose the specific commit you want to run.
* Package path: A path within the code repository where packages included in the main script are located.
* Code module: The name of the file that should be executed. E.g. if you locally would run `python mnist.py`, your code module name is `mnist`.

## Datasets

The data that your job operates on. See [here](doc:data-on-clusterone) to learn more about datasets on Clusterone.

## Python Environment and Machine Learning Framework

* Python version: Clusterone supports Python 2.7 and 3.5.
* Framework type and version: Clusterone supports different machine learning frameworks and versions of them. See [here](doc:supported-frameworks) to learn more.
* Package manager: Clusterone supports different Python package managers. See [here](doc:package-management) to learn more.
* Requirements file: Package managers read this file to know which Python packages to lead.

## Hardware Resources

* Single or Distributed: Clusterone supports running code on single machines, as well as distributed computing based on [data parallelism](https://en.wikipedia.org/wiki/Data_parallelism).
* Number and type of instances: Clusterone offers different types of hardware instances. See [here](doc:hardware-instance-types) to learn more.

## Job Metadata

* Name: Give your job a unique name to remember it by.
* Description: Describe what your job does or how it differs from other jobs.
* Maximum runtime: The maximum time after which your job is terminated if it didn't finish before.

## Custom Arguments

Custom arguments can be passed to the Python file that is being executed. [See here](doc:custom-job-parameters) for more information.

