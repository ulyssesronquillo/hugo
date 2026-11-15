---
title: 'empty a file'
author: ulysses

date: 2017-12-21
slug: empty-a-file
draft: false
---

If you work with vi, nano or any other command line editor, deleting a line is a fairly easy thing to do. If the file is too large, deleting the content line by line is not fun. There’s a better way to empty a file without deleting it. Here are several ways.

```
$ > filename
$ truncate -s 0 filename
$ echo "" > filename
```