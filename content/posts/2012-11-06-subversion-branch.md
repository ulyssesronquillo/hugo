---
title: 'subversion branch'
author: ulysses

date: 2012-11-06
slug: subversion-branch
draft: false
---

Subversion Branch creates a new branch in the local working directory. In the example below, a copy of the project directory is forked and given a new name. The new branch will be treated as a separate branch.

```
svn copy http://repository/project/trunk \ 
         http://repository/project/branch/newbranch 
         \ -m "Place comments here."
```