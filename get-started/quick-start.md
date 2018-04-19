---
title: Quick Start
description: Get started with Clusterone
---

# Quick Start

This guide will get you started with Clusterone. We'll start with a hands-on example on this page to get you working in no time. Don't worry if the commands on this page don't make sense to you, you'll learn what they mean on the next pages.

To keep things simple, we'll show you how to use Clusterone using a ready-to-run demo of handwritten digit recognition using the MNIST dataset.

Ready to get going? Let's dive in!

## Prerequisites

Before we begin, make sure you have all your gear ready:

* A Clusterone account. Go [create one](https://www.clusterone.com) if you haven't yet!
* Make sure you have [Python](https://python.org) 3.5 installed.
* Install [Git](https://git-scm.com)
* Install the Clusterone Python package. It's as easy as `pip install clusterone`

## In a Nutshell

These instructions use the `just` command line tool. It comes with the Clusterone Python library and is installed automatically with the library. Clusterone also provides a graphical web interface, the [Matrix](https://clusterone.com/matrix). We'll get to that [later](doc:watch-your-job-progress-and-access-results).

For now, open a command line and start by getting our MNIST source code from the [GitHub repository](https://github.com/clusterone/mnist):

```bash
git clone https://github.com/clusterone/mnist
```

Navigate into the folder you just cloned:

```bash
cd mnist
```

Next, log into your Clusterone account:

```bash
just login
```

Create a new project on Clusterone:

```bash
just init project mnist
```

Then, upload the code to your new project:

```bash
git push clusterone master
```

{% hint style="info" %}
There is a slight delay of a few seconds until the commits are available on the system. If creating your job fails with an error stating `This project has no commits, cannot proceed`, simply wait for a few seconds and try again.
{% endhint %}

Now, create a job:

```bash
just create job distributed --project mnist --module mnist --name first-job --time-limit 1h
```

Finally, all that's left to do is starting the job:

```bash
just start job -p mnist/first-job
```

That's it! You can monitor the status of your job on the command line using `just get events`. More elaborate monitoring is available on the [Matrix](https://clusterone.com/matrix), Clusterone's graphical web interface, including automatic integration with TensorBoard. 

## Learn More

Now that you have run your first job on Clusterone, it's time to learn more about the platform.

On the following pages, we'll show you more about creating projects and datasets, and how to run them on Clusterone. Finally, we will take you for a tour around Clusterone's graphical interface and show you how to access TensorBoard right from your project.

_Join our _[_Slack_](http://slack.clusterone.com)_ to get support and tips from the community._

