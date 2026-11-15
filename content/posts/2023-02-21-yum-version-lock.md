---
title: 'yum version lock'
author: ulysses

date: 2023-02-21
slug: yum-version-lock
draft: false
---

How to lock a package or software in RedHat.

```
# For RHEL 5
yum install yum-versionlock
# For RHEL 6 and 7
yum install yum-plugin-versionlock
# For RHEL 8 and 9
yum install python3-dnf-plugin-versionlock
```

Locking a package

```
yum versionlock gcc-*
```

List locked packages

```
yum versionlock list
```