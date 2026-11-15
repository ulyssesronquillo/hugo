---
title: 'install pint on sles'
author: ulysses

date: 2023-08-28
slug: install-pint-on-sles
draft: false
---

How to install pint utility on SLES machines.

```
zypp in python-susepubliccloudinfo
```

Once installed, you can run

```
pint amazon servers –region='us-east-1'
pint google servers –region='us-central1'
pint microsoft servers –region='eastus'
```