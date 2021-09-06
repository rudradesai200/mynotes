---
title: "How to Use Git and Github-cli"
draft: false
description: ""
date: 2021-06-17T09:55:00+05:30
lastmod: 2021-06-17T09:55:00+05:30
tags: ["how-to","setup","git","github"]

# Theme-Defined params
comments: true # Enable/disable Disqus comments for specific page
authorbox: false # Enable/disable Authorbox for specific page
toc: false # Enable/disable Table of Contents for specific page
tocOpen: false # Open Table of Contents block for specific page
mathjax: true # Enable/disable MathJax for specific page
related: true # Enable/disable Related content for specific page
---

Some of the frequently used git commands along with some advanced git stuff.

<!--more-->

### Setting up git and github-cli
- `sudo apt install git-all` : Install git
- `conda install gh --channel conda-forge` : Install github-cli
- `ssh-keygen -t rsa -C <emailId>` : Creates a ssh key in ~/.ssh
- `gh ssh-key add <path> -t <title>` : Adds the given public key on github with title <title>
- After these steps, one can directly clone the github using the SSH url.
- The SSH keys takes care of multi/2 FA auth and only password will be asked while git operations.

### Basic Git commands
- `git clone <url> <path>` : Clones the repo to the specified path. Options 
    - `-b` : Clones the particular branch
    - `-o` : Clones the particular origin
    - `--recurse-submodules` : Clones the submodules as well
- `git add <path>` : Adds the changes in the <path> to the staging area
- `git commit <path> -m <message>` :  Commits the changes on the <path> with the <message>
- `git push <remote> <branch>` : Pushes the commits to <remote>/<branch>. Default, <remote>=origin, <branch>=main. Options
    - `-u/--set-upstream` : Pushed the commits + sets the upstream for the current branch
    - `-d/--delete` : Deletes the <branch> in the remote repository
- `git pull <remote> <branch>` : Pulls the commits from the <remote>/<branch>
- `git checkout <branch>` : Switches to the <branch> locally
    - `-b` : Creates a new branch and switches to it
- `git branch` : List, create or delete branches
    - `-d <branch>` : Deletes <branch> locally.
    - `--list` : Lists all the available branches locally.
    - `-m/-M <oldbranch> <newbranch>` : Renames the <oldbranch> to <newbranch>
- `git submodule` : Initialize, update or inspect submodules
    - `add <url> <path>` : Adds a new submodule to the specified path and adds an entry in `.gitmodules`
    - `status` : Shows the status of all the submodules in the current repo
    - `init <path>` : Initializes a submodule on the specified <path> and updates it in `.git/config`
    - `deinit <path>` : Unregisters a submodule on the specified <path> and removes it from `.git/config`
    - `update` Update the registered submodules to match what the superproject expects by cloning missing submodules, fetching missing commits in submodules and updating the working tree of the submodules. Following options are supported
        - `--rebase` : the current branch of the submodule will be rebased onto the commit recorded in the superproject.
        - `--merge` : the commit recorded in the superproject will be merged into the current branch in the submodule.
        - `--checkout` : the commit recorded in the superproject will be checked out in the submodule on a detached HEAD.


### Basic Github-cli commands
- `gh repo` : Works with Github Repositories
    - `clone` : Clones the repo
    - `create` : Creates a new repo in the pwd
    - `list` : Lists all the repos
    - `view <name>` : Views a repo
- `gh secret` : Works with Github Repo Secrets
- `gh ssh-key` : Works with github ssh keys

