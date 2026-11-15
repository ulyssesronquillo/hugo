---
title: 'aws cli efs describe tags'
author: ulysses

date: 2019-02-24
slug: aws-cli-efs-describe-tags
draft: false
---

How to display tags of EFS file system.

```
aws efs describe-tags \
--file-system-id fs-xxxxxxxx \
--query 'Tags[?Key==`tagname`].{Name:Key,Value:Value}'
```