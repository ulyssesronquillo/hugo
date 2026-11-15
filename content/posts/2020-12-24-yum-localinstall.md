---
title: 'yum localinstall'
author: ulysses

date: 2020-12-24
slug: yum-localinstall
draft: false
---

Here’s how to install a RPM locally. Download the RPM first.

```
wget https://domain.com/path/to/file/rpmfile1.rpm
wget https://domain.com/path/to/file/rpmfile2.rpm
```

Then install RPM from a local file.

```
yum localinstall /path/to/rpmfile1.rpm
yum localinstall /path/to/rpmfile2.rpm
```