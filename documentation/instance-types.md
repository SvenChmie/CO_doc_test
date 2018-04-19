---
title: "Instance Types"
excerpt: ""
---
Clusterone offers a variety of different instance types to run your models on. On the public platform, Clusterone provides [AWS](https://aws.amazon.com) instances. For Clusterone Enterprise, instances from any cloud provider are supported.
[block:api-header]
{
  "title": "Purchasing options"
}
[/block]
There are two main compute options on Clusterone:
- blessed instances (default): reliable, with a 99.9% uptime guarantee
- spot instances: can be interrupted at any time. Clusterone automatically manages restart of interrupted jobs.
[block:api-header]
{
  "title": "Naming conventions"
}
[/block]
Instances are named after their type. Spot instances are identified by a trailing "-spot": <instance-type>[-spot].
Naming examples:
- blessed: `c4.2xlarge`
- spot: `c4.2xlarge-spot`

[block:api-header]
{
  "title": "Instance characteristics"
}
[/block]
The table below provides an overview of the instance types Clusterone offers on its public platform, as well as the supported framework versions. For information on pricing for these instances see our [pricing page](https://clusterone.com/pricing).
[block:parameters]
{
  "data": {
    "h-0": "Instance Name",
    "h-1": "CPUs",
    "h-2": "GPUs",
    "h-3": "Memory",
    "h-4": "GPU Type",
    "h-5": "Supported Frameworks",
    "0-0": "t2.small",
    "0-1": "1",
    "0-2": "None",
    "0-3": "2GiB",
    "0-4": "None",
    "0-5": "All",
    "1-0": "p2.xlarge",
    "1-1": "4",
    "1-2": "1",
    "1-3": "61GiB",
    "1-4": "NVIDIA K80",
    "1-5": "PyTorch, TensorFlow up to v1.4",
    "2-0": "p3.2xlarge",
    "2-1": "8",
    "2-2": "1",
    "2-3": "61GiB",
    "2-4": "NVIDIA Tesla V100",
    "2-5": "All",
    "3-0": "c4.2xlarge",
    "3-1": "8",
    "3-2": "None",
    "3-3": "15GiB",
    "3-4": "None",
    "3-5": "All",
    "h-6": "Purchase Options",
    "0-6": "Blessed, Spot",
    "1-6": "Blessed",
    "2-6": "Blessed",
    "3-6": "Blessed, Spot"
  },
  "cols": 7,
  "rows": 4
}
[/block]
For further information about each instance type, visit the [AWS website](https://aws.amazon.com/ec2/instance-types/).

[block:api-header]
{
  "title": "Spot instances"
}
[/block]
Spot instances are spare capacity that is sold at a discount but can be interrupted at any time. 

On AWS, you lose a spot instance when it is drained and you have to bid for a new one. In contrast, Clusterone automatically and continuously bids for spot instances, ensuring availability. 

Jobs running on spot instances that are interrupted are automatically restarted, meaning you can run jobs on spot instances without constantly monitoring them. When a spot instance is drained, Clusterone will procure additional instances, and restart the job. 

Provided you are using checkpoints, even large-scale long-running workloads do not require any setup or monitoring when running on spot instances.