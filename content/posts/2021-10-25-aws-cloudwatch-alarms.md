---
title: 'aws cloudwatch alarms'
author: ulysses

date: 2021-10-25
slug: aws-cloudwatch-alarms
draft: false
---

How to enable and disable CloudWatch alarms

```
$ aws cloudwatch disable-alarm-actions --alarm-names myalarm --region us-east-1
$ aws cloudwatch enable-alarm-actions --alarm-names myalarm --region us-east-1
```