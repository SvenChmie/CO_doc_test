---
title: EFS Datasets
excerpt: EFS Datasets on Clusterone Enterprise
---

# EFS Datasets

\[block:callout\] { "type": "info", "title": "Clusterone Enterprise Only", "body": "This feature is only available on some Clusterone Enterprise installations. Contact your account administrator for details." } \[/block\] Jobs on Clusterone can use data stored on Amazon's [Elastic File System](https://aws.amazon.com/efs/) \(EFS\) service.

Your EFS drives are integrated into your Clusterone Enterprise setup upon installation. After the installation is complete, your EFS drives are automatically mounted to each pod created by Clusterone.

\[block:api-header\] { "title": "Runtime" } \[/block\] If you have an EFS dataset, it will become available in `/data/` at runtime by default. There is no need to add the dataset to the job specification.

As EFS datasets are mounted on the pods, data is _not_ copied from the dataset to the pod at runtime. Changes made to `/data/` are transparently made to the data. \[block:callout\] { "type": "warning", "body": "Note that modifying an EFS file while running a job reading it may result in the job to fail. Make sure no other user is modifying a file if you use it for a job.", "title": "EFS data at runtime" } \[/block\] This page describes the default configuration, please contact your administrator for specifics on how data is managed in your Clusterone Enterprise installation.

