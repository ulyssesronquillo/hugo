---
title: 'subversion add'
author: ulysses

date: 2012-10-26
slug: subversion-add
draft: false
---

Adding a file or directory to Subversion is quite easy. The following commands will add a file and a directory to the current Subversion working directory. The added file or directory is only added to the local working directory, and not to the Subversion repository. For that to happen, you’ll need to issue a Subversion commit to synch the files to the repository. The following commands simply add files and directories in the local working directory.

Add a file

```
svn add foo.c
```

Add a directory

```
svn add directory
```
