---
title: Package Management
excerpt: Manage Python requirements with the most popular package managers
---

# Package Management

Clusterone supports two package managers: [pip](doc:managing-packages-with-pip) and [anaconda](doc:anaconda).

Regardless of which package manager you use, the requirements should be defined in a `requirements.txt` \(pip\) or `requirements.yml` \(conda\) file in your project and uploaded to Clusterone. When a job is launched, requirements will be read from this file and installed on the instances\(s\).

The installation logs will show up in the outputs when you run a job: \[block:image\] { "images": \[ { "image": \[ "[https://files.readme.io/8e5ecef-package-manager-log.png](https://files.readme.io/8e5ecef-package-manager-log.png)", "package-manager-log.png", 1966, 900, "\#242434" \] } \] } \[/block\]

