---
title: 'zip multiple files into one zip'
author: ulysses

date: 2021-12-31
slug: zip-multiple-files-into-one-zip
draft: false
---

How to zip multiple files into one zip file.

Using zip.

```
zip test.zip *.txt
```

Using tar.

```
tar cvzf test.tar.gz *.txt
```

Untar in current directory or specify another directory.

```
tar xvzf test.tar.gz .
tar xvzf test.tar.gz -C /path/to/dir
```