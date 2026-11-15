---
title: 'rpm check packages'
author: ulysses

date: 2019-02-20
slug: rpm-check-packages
draft: false
---

How to check RPM if packages are installed.

```
rpm -qa --last 
rpm -qa --last | more
rpm -qa --last | grep "package name"
```