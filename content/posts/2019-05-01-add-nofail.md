---
title: 'add nofail'
author: ulysses

date: 2019-05-01
slug: add-nofail
draft: false
---

The /etc/fstab file allow volumes to be automatically mounted on bootup. Add nofail in your automated mounts to prevent instances from hanging on boot. Nofail makes the instance to boot even if there are errors with the mounted volume.

```
UUID=aebf131c-6957-451e-8d34-ec978d9581ae  /data  xfs  defaults,nofail  0  2
```