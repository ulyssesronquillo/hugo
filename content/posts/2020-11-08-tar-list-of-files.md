---
title: 'tar list of files'
author: ulysses

date: 2020-11-08
slug: tar-list-of-files
draft: false
---

Here’s another way of creating a tar ball from a list of files.

```
tar -cvf backup.tar.gz a.txt b.txt c.txt d.txt e.txt
```

Here’s how to view files in a tarball.

```
tar -tvf backup.tar.gz
```