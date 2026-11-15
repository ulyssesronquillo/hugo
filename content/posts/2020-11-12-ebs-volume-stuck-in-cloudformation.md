---
title: 'ebs volume stuck in cloudformation'
author: ulysses

date: 2020-11-12
slug: ebs-volume-stuck-in-cloudformation
draft: false
---

When running CloudFormation, all the resources are being created with no problem. However it seems to be getting stuck at creating or mounting a volume. The CloudFormation fails and initiates a rollback. This is the error I am getting.

```
Volume attachment between volume-id vol-xxxxxxxx and instance-id i-xxxxxxx at device /dev/xvda is attaching
```

This turned out to be a conflict on HVM EC2 instances because /dev/sda1 is being remapped to /dev/xvda. My second drive is also mapped to /dev/xvda. The fix was to simply to map it slightly different to avoid mapping conflict.

Here’s the original mapping.

```
Boot:   /dev/xvda
Device: /dev/xvda
Device: /dev/xvdb
```

Here’s the fix.

```
Boot:   /dev/xvda
Device: /dev/xvdb
Device: /dev/xvdc
```