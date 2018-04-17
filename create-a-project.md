---
title: Create a Project
excerpt: ''
---

# Create a Project

On Clusterone, code repositories are called _projects_. First, we'll show you how to create a new project. Then, we'll push an existing Git repository to Clusterone to fill your project with life. \[block:callout\] { "type": "info", "body": "Projects on Clusterone can either contain their own Git repository or link to a repository on GitHub. Here we're using the former. For an explanation of how to link your GitHub repository to Clusterone, [see here](doc:github-repositories).", "title": "GitHub repositories" } \[/block\] In this guide, we are using the MNIST demo repository that you downloaded in the beginning.

On the command line, navigate into the folder of the repository:

```bash
$ cd mnist
```

Log into your Clusterone account:

```bash
$ just login
```

The program will prompt you for your username and password. Note: Your username is not your email address, but the name you provided upon registration! \[block:api-header\] { "title": "Create a new project with the CLI" } \[/block\] There are two ways to create a project with the CLI:

* `just create project` does exactly what it says, it creates a new project on Clusterone and nothing else. Use this command when you want to import code from remote locations like Github. 
* `just init project` creates a project and then adds a git remote to the Git repository in the current folder. Use this command to import code from your local machine.

In this example, we already have our code in a Git repository on our local machine, so `just init` is the way to go. Make sure you do `cd mnist`, then create a new project:

```bash
$ just init project mnist
```

Note that the project name needs to be unique for your account. If you already have a project called `mnist` and you're trying to create another one, `just` will report an error.

\[block:api-header\] { "title": "Push code to Clusterone" } \[/block\] Clusterone uses Git to manage your project's source code. When creating a project in a git repository using `just init`, a Git remote called _clusterone_ is automatically added.

All you need to do to push the code to your Clusterone project is this:

```bash
$ git push clusterone master
```

You can check that your project was created by listing all your projects:

```bash
$ just get projects
```

Alternatively, navigate to [clusterone.com/matrix](http://www.clusterone.com/matrix). You'll see that the project has been added to your Clusterone account.

