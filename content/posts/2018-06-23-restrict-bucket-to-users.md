---
title: 'restrict bucket to users'
author: ulysses

date: 2018-06-23
slug: restrict-bucket-to-users
draft: false
---

How to restrict a S3 bucket to certain group of users. Edit the bucket policy and add the following.

```
{
    "Version": "2012-10-17",
    "Id": "bucketPolicy",
    "Statement": [
        {
            "Effect": "Deny",
            "NotPrincipal": {
                "AWS": "arn:aws:iam::xxxxxxxxxx:user/username",
                "AWS": "arn:aws:iam::xxxxxxxxxx:root",
            },
            "Action": "s3:*",
            "Resource": [
                "arn:aws:s3:::bucketname",
                "arn:aws:s3:::bucketname/*"
            ]
        }
    ]
}
```

Replace xxxxxxxxxx with your AWS account number.  
Replace bucketname with your S3 bucket.  
Replace username with your IAM user.  
Root is your AWS root account.  
Accounts must be valid.