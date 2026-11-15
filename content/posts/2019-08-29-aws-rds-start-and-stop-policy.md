---
title: 'aws rds start and stop policy'
author: ulysses

date: 2019-08-29
slug: aws-rds-start-and-stop-policy
draft: false
---

Here’s a IAM policy that you can add to an IAM user or an IAM role so they are able to start and stop a specific RDS instance.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Condition": {
                "StringEqualsIgnoreCase": {
                    "rds:db-tag/Application": "application-name"
                }
            },
            "Action": [
                "rds:DescribeDBInstances",
                "rds:StartDBInstance",
                "rds:StopDBInstance"
            ],
            "Resource": "arn:aws:rds:us-east-1:xxxxxxxxxxxx:db:db-instance-name",
            "Effect": "Allow"
        }
    ]
}
```