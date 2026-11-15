---
title: 'aws cli efs describe file systems'
author: ulysses

date: 2019-02-24
slug: aws-cli-efs-describe-file-systems
draft: false
---

Show a list of EFS file systems within a region.

```
aws efs describe-file-systems \
--region us-east-1
```

Filter by Name and FileSystemId.

```
aws efs describe-file-systems \
--query 'FileSystems[*].[Name,FileSystemId]'
```