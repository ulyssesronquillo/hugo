---
title: 'removing old kernels'
author: ulysses

date: 2019-06-10
slug: removing-old-kernels
draft: false
---

How to check which kernel is running on your system

```
uname -sr
```

List all kernels installed on the system.

```
rpm -q kernel
```

Removing old kernels using package-cleanup. This keeps 2 kernels on the system.

```
yum install yum-utils
package-cleanup --oldkernels --count=2
```