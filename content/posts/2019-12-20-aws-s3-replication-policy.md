---
title: 'aws s3 replication policy'
author: ulysses

date: 2019-12-20
slug: aws-s3-replication-policy
draft: false
---

Here’s the policy for S3 replication between regions.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "s3:Get*",
                "s3:ListBucket"
            ],
            "Effect": "Allow",
            "Resource": [
                "arn:aws:s3:::source-bucket-name",
                "arn:aws:s3:::source-bucket-name/*"
            ]
        },
        {
            "Action": [
                "s3:ReplicateObject",
                "s3:ReplicateDelete",
                "s3:ReplicateTags",
                "s3:GetObjectVersionTagging"
            ],
            "Effect": "Allow",
            "Resource": "arn:aws:s3:::destination-bucket-name/*"
        }
    ]
}
```