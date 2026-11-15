---
title: 'subversion import'
author: ulysses

date: 2012-11-02
slug: subversion-import
draft: false
---

Typically, you use the Subversion Import command to start or add a new project to a remote repository. Subversion recommends that you setup three directories called trunk, tags and branches under each project in a repository. Trunk will be the current version you are working on. Tags are for releases. Branches are when you fork projects based on one particular release. The following directory format under each project is recommended.

```
repository/project/trunk
                  /tags
                  /branches
```

Once the directories are setup, you can then perform the import command to upload a new project to the repository. Just the following command in the Terminal.

```
svn import project http://repository -m "Place comments here."
```