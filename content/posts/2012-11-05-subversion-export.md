---
title: 'subversion export'
author: ulysses

date: 2012-11-05
slug: subversion-export
draft: false
---

Subversion Export creates a clean working copy of a project without the .svn folders and files. In this example, the command creates a folder named `project` and places a clean working copy in it.

```
svn export http://repository/project/trunk project
```