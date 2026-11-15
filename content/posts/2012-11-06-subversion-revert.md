---
title: 'subversion revert'
author: ulysses

date: 2012-11-06
slug: subversion-revert
draft: false
---

Subversion Revert undoes the recent changes in the local working directory. Revert can also undo changes recursively. Here’s a couple of examples displayed below.

```
svn revert foo.c
svn revert --recursive .
```