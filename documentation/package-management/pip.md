---
title: pip
excerpt: ''
---

# pip

To use pip as a package manager, you need to define your requirements in a `requirements.txt` file and add it to your Project on Clusterone. For example: \[block:code\] { "codes": \[ { "code": "h5py==2.7.0\nscikit-image==0.13.0\nscikit-learn==0.18.1\nnumpy==1.12.1\nscipy==0.19.0", "language": "text", "name": "requirements.txt" } \] } \[/block\]

\[block:callout\] { "type": "info", "title": "Local check", "body": "You can check locally that this file is valid by running: `pip install -r requirements.txt`" } \[/block\] After this file has been added to your project code, you will need to specify it when running a job. \[block:api-header\] { "title": "From the GUI" } \[/block\] At the Environment step, select pip as the package manager. `requirements.txt` is the default name for the requirements file, update it as needed. \[block:image\] { "images": \[ { "image": \[ "[https://files.readme.io/f0ec9c0-job-wizard-pip.png](https://files.readme.io/f0ec9c0-job-wizard-pip.png)", "job-wizard-pip.png", 1974, 1274, "\#252737" \] } \] } \[/block\]

\[block:api-header\] { "title": "From the CLI" } \[/block\] The `just run` command defaults to pip, assuming a `requirements.txt` file. If no file is found, no requirements will be installed.

To be explicit use `just run` with the `package-manager pip --requirements requirements.txt` option.

