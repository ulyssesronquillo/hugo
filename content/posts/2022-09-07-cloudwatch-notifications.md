---
title: 'cloudwatch notifications'
author: ulysses

date: 2022-09-07
slug: cloudwatch-notifications
draft: false
---

How to give someone access to enable/disable CloudWatch notifications.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "cloudwatch:DescribeAlarms",
                "cloudwatch:EnableAlarmActions",
                "cloudwatch:DisableAlarmActions"
            ],
            "Effect": "Allow",
            "Resource": "*"
        }
    ]
}
```