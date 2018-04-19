---
title: "Projects on Clusterone"
excerpt: ""
---
Code on Clusterone is organized into projects. Each project contains code stored in a Git repository. To run the code, you have to create a job within the project.

There are two types of projects: 
- Projects with code hosted on Clusterone
- Projects linking to a GitHub repository

Both types are used in the same way when creating and running jobs. However, there are a few differences regarding the functions they support. See the table below for a list of the differences.
[block:api-header]
{
  "title": "Feature Comparison"
}
[/block]
To make it easier for you to decide if you should host your code on Clusterone or GitHub, here's a table comparing the available features for each type of project.
[block:parameters]
{
  "data": {
    "h-1": "Hosted on ClusterOne",
    "h-2": "GitHub",
    "0-0": "**Location of the code** ",
    "0-1": "Clusterone git server",
    "0-2": "GitHub",
    "1-0": "**Run jobs** ",
    "1-1": "Yes",
    "1-2": "Yes",
    "2-0": "**View code** ",
    "2-1": "On Clusterone",
    "2-2": "On Clusterone, On GitHub",
    "3-0": "**Push new commits** ",
    "3-2": "Through GitHub",
    "3-1": "Through the CLI",
    "h-0": "Feature",
    "4-0": "**Sharing** ",
    "4-1": "Natively on Clusterone",
    "4-2": "Limited by underlying GitHub permissions",
    "6-0": "**Delete Project** ",
    "6-1": "Code fully deleted",
    "6-2": "Clusterone project deleted, GitHub repository not modified",
    "5-0": "**Create Project**",
    "5-1": "CLI, GUI, API",
    "5-2": "Link from the Matrix"
  },
  "cols": 3,
  "rows": 7
}
[/block]