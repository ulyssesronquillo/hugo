---
title: 'aws search for rds'
author: ulysses

date: 2022-01-03
slug: aws-search-for-rds
draft: false
---

Here’s a simple way to search for a RDS instance in AWS via CLI.

```
aws rds describe-db-instances \
--db-instance-identifier rds-instance-name \
--region us-east-1 \
--profile my-account
```

You may have to cycle through accounts and regions to find it.