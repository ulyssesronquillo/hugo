---
title: 'aws efs describe mount targets'
author: ulysses

date: 2019-11-04
slug: aws-efs-describe-mount-targets
draft: false
---

Here’s how to display mount targets of an EFS system via AWS CLI.

```
aws efs describe-mount-targets \
--file-system-id fs-xxxxxxxx \
--profile default \
--region us-east-1
```