---
title: 'count number of files in directory'
author: ulysses

date: 2019-05-14
slug: count-number-of-files-in-directory
draft: false
---

Get a count of the number of files in a directory.

```
# using ls
ls | wc -l
ls -Aq | wc -l
# include hidden files 
find . ! -name . -prune -print | grep -c /
find .//. ! -name . -print | grep -c //
# using tree if installed. yum install tree. apt-get install tree
tree 
```