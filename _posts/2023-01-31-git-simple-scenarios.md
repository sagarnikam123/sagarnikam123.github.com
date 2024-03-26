---
layout: post
title: "Git - simple workflows"
description: "example code for daily activity"
category: [git]
tags: [git, guide]
---
{% include JB/setup %}


While working with code, respository and collaboration through git, encounters simple workflow or process.

- **pull specific branch**
```
# clone the remote master/main
git clone <remote url>
# checkout to a branch
git checkout <remote_branch_name>
# pull the code 
git pull origin "<local_branch_name>"
```

- **create new branch from specific one on local**
```
# go to the branch from which you want to create the new branch
git checkout <existing-branch>
# create a new branch
git branch <new-branch>
# Switch to the new branch 
git checkout <new-branch>
# Make changes & commit to the new branch as needed
git commit -m "<Commit message>"
# push the new branch to a remote repository
git push -u origin <new-branch>
```
