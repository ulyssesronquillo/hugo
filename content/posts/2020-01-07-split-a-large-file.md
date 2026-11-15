---
title: 'split a large file'
author: ulysses

date: 2020-01-07
slug: split-a-large-file
draft: false
---

How to split a large file.

```
split -b 500MB httpd.log
ll -lh
total 1.9G
-rw-r--r-- 1 root root 954M Mar 25 12:35 httpd.log
-rw-r--r-- 1 root root 477M Mar 25 12:38 xaa
-rw-r--r-- 1 root root 477M Mar 25 12:38 xab
```

Split with an output file.

```
split -b 200M httpd.log split.log
ll -lh
total 1.9G
-rw-r--r-- 1 root root 954M Mar 25 12:35 httpd.log
-rw-r--r-- 1 root root 200M Mar 25 12:52 split.logaa
-rw-r--r-- 1 root root 200M Mar 25 12:52 split.logab
-rw-r--r-- 1 root root 200M Mar 25 12:52 split.logac
-rw-r--r-- 1 root root 200M Mar 25 12:52 split.logad
-rw-r--r-- 1 root root 154M Mar 25 12:52 split.logae
```