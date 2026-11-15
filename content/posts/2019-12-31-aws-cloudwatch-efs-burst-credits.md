---
title: 'aws cloudwatch efs burst credits'
author: ulysses

date: 2019-12-31
slug: aws-cloudwatch-efs-burst-credits
draft: false
---

Here’s how to get the EFS Burst Credits from CloudWatch via AWS CLI.

```
aws cloudwatch get-metric-statistics \
--namespace "AWS/EFS" \
--metric-name BurstCreditBalance \
--dimensions "Name=FileSystemId,Value=fs-xxxxxxx" \
--start-time 2019-12-31T00:00:00Z \
--end-time 2019-12-31T01:00:00Z \
--statistics Average \
--period 3600 \
--profile default
```

Notice the start time, end time, period and statistics. Here’s the CLI [doc](https://docs.aws.amazon.com/cli/latest/reference/cloudwatch/get-metric-statistics.html).