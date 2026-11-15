---
title: 'aws get access key info'
author: ulysses

date: 2022-06-28
slug: aws-get-access-key-info
draft: false
---

How to look for an access key in AWS. Find the account.

```
$ aws sts get-access-key-info --access-key-id AKIA8XXXXXXXXXXXXXXX
{
    "Account": "XXXXXXXXXXXX"
}
```