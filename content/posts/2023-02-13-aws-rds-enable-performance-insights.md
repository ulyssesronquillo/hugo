---
title: 'aws rds enable performance insights'
author: ulysses

date: 2023-02-13
slug: aws-rds-enable-performance-insights
draft: false
---

Here’s how to enable performance insights on a RDS instance.

Enable

```
aws rds modify-db-instance \
--db-instance-identifier sample-db-instance \
--enable-performance-insights \
--region us-east-1 \
--profile default
```

Disable

```
aws rds modify-db-instance \
--db-instance-identifier sample-db-instance \
--no-enable-performance-insights \
--region us-east-1 \
--profile default
```