---
title: View your Job and Results
excerpt: ''
---

# View your Job and Results

As soon as you start the job in Clusterone, it will gather the necessary resources and start once all resources are available. 

##Follow Job Progress on the Matrix

The Clusterone Matrix provides multiple ways to examine your job's status. Click the "See Details" button under the name of your job to see how it's doing.

The "Events" tab provides a graphical representation of the startup progress of the job. Four circles allow you to see at a glance if your job has gathered all the resources it needs, or what is still missing. 

![](/.gitbook/assets/ffad482-Waiting_for_Resources.JPG)

* The **Creation Status** tells you if the job has been created.
* The **Computational Requirements** circle lists all required workers and parameter servers. It also contains information if the workers are running or if your job is still waiting for workers to become available.
* The **Code Cloning** circle tell you if the repository code has been successfully cloned onto the worker machines.
* The **Process Start-Up** circle represents the overall status of the job. Once the job has started, it will say "Running".

The "Outputs" tab contains a list of all raw output files that are generated while running the job. Here you can find the log files for each worker, event log files, and more. Click on each file to open it, or follow the download link on the right to download the file. 

## Follow Job Progress on the Command Line

The `just` command line tool enables you to monitor a running job from the command line. Use `just get events` to print a list of your recent job executions and their status.

See the [CLI documentation](doc:just-cli-reference-manual) for more info on how to use the `just` command. \



##Connect to TensorBoard

Clusterone provides direct access to [TensorBoard](https://www.tensorflow.org/get_started/summaries_and_tensorboard), TensorFlow's suite of visualization tools.

To add your running job to TensorBoard, click the "Add to TensorBoard" button right next to the "Pause" button. Your job is now available on TensorBoard.

To access TensorBoard, click the TensorBoard button on the top bar. You can observe how well the model trained using the `Training_Loss` and `Validation_Loss` curves on the "Scalars" page of TensorBoard.

You can further examine a graph representation of the model on the "Graph" page. 

{% hint style="info" %}

You can use TensorBoard with other deep learning frameworks too. See [this GitHub project](https://github.com/lanpa/tensorboard-pytorch) for a PyTorch TensorBoard API.

{% endhint %}

##Ready for More?

In this guide, you have learned how to set up your first project on Clusterone, how to run it, and how you can examine its results. What's next?

If you're looking for another use case example, you can follow our [DCGAN tutorial](doc:creating-celebrity-faces-using-a-dcgan). In this more complex example, we run a Deep Convolutional GAN and generate artificial celebrity faces based on the celebA dataset.

If you want to learn more about a specific part of Clusterone, check out our [Documentation Homepage](https://docs.clusterone.com) with articles on all the details of running state-of-the-art distributed machine learning models on Clusterone.

Or jump right in and run your own project. If you have any comments, questions, or concerns, please don't hesitate to [contact us](https://clusterone.com/contact/), we'd love to hear from you!

_Also, make sure to join our _[_Slack_](http://slack.clusterone.com)_ to get support and tips from the community!_

