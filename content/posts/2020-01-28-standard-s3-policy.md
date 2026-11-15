---
title: 'standard s3 policy'
author: ulysses

date: 2020-01-28
slug: standard-s3-policy
draft: false
---

Here’s a standard S3 policy to grant an IAM user access to a bucket within an AWS account. User is allowed to add, update, and delete objects. These 3 actions s3:ListAllMyBuckets, s3:GetBucketLocation, and s3:ListBucket are the additional permissions required to access the console. Also, the s3:PutObjectAcl and the s3:GetObjectAcl actions are required to be able to copy, cut, and paste objects within the console.

```
{
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListAllMyBuckets"
         ],
         "Resource":"arn:aws:s3:::*"
      },
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket",
            "s3:GetBucketLocation"
         ],
         "Resource":"arn:aws:s3:::examplebucket"
      },
      {
         "Effect":"Allow",
         "Action":[
            "s3:PutObject",
            "s3:PutObjectAcl",
            "s3:GetObject",
            "s3:GetObjectAcl",
            "s3:DeleteObject"
         ],
         "Resource":"arn:aws:s3:::examplebucket/*"
      }
   ]
}
```