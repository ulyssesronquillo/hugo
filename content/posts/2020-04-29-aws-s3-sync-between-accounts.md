---
title: 'aws s3 sync between accounts'
author: ulysses

date: 2020-04-29
slug: aws-s3-sync-between-accounts
draft: false
---

Here’s how to sync S3 buckets between 2 different AWS accounts. Assuming buckets are already created.

1. Setup bucket permissions in Account A
2. Setup IAM user with permissions in Account B
3. Setup bucket permissions in Account B
4. Run S3 sync from Account B.

Account A bucket permissions. Account and user are from Account B.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "DelegateS3Access",
            "Effect": "Allow",
            "Principal": {"AWS": "arn:aws:iam::222222222222:user/Jane"},
            "Action": ["s3:ListBucket","s3:GetObject"],
            "Resource": [
                "arn:aws:s3:::awsexamplesourcebucket/*",
                "arn:aws:s3:::awsexamplesourcebucket"
            ]
        }
    ]
}
```

Create IAM user (Jane) in Account B

```
aws iam create-user --user-name Jane
```

Give IAM user (Jane) access to both buckets.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket",
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::awsexamplesourcebucket",
                "arn:aws:s3:::awsexamplesourcebucket/*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket",
                "s3:PutObject",
                "s3:PutObjectAcl"
            ],
            "Resource": [
                "arn:aws:s3:::awsexampledestinationbucket",
                "arn:aws:s3:::awsexampledestinationbucket/*"
            ]
        }
    ]
}
```

Sync the buckets

```
aws s3 sync s3://awsexamplesourcebucket s3://awsexampledestinationbucket
```