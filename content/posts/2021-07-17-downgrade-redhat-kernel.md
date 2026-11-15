---
title: 'downgrade redhat kernel'
author: ulysses

date: 2021-07-17
slug: downgrade-redhat-kernel
draft: false
---

How to downgrade a Redhat kernel within the same release.

List kernel.

```
yum list kernel-3.10.0-862*
yum list kernel-3.10*
```

Install previous kernel if missing.

```
yum install kernel-3.10.0-862.el7
```

Downgrade to next minor release.

```
yum downgrade redhat-release
```