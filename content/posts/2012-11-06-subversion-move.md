---
title: 'subversion move'
author: ulysses

date: 2012-11-06
slug: subversion-move
draft: false
---

Subversion Move is a command that renames a file in either in the local working directory or directly in the repository. You can invoke the move command from Terminal like this example below.

```
svn move foo.c bar.c
svn move http://repository/project/trunk/foo.c \ 
    http://repository/project/trunk/bar.c 
    -m "Place comment here."
```