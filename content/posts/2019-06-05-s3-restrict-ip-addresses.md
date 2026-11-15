---
title: 's3 restrict ip addresses'
author: ulysses

date: 2019-06-05
slug: s3-restrict-ip-addresses
draft: false
---

Here’s the policy to restrict access to S3 bucket to certain IP addresses.

```
{
    "Version": "2012-10-17",
    "Id": "S3PolicyIPRestrict",
    "Statement": [
        {
            "Sid": "IPAllow",
            "Effect": "Allow",
            "Principal": {
                "AWS": "*" 
            },
            "Action": "s3:*",
            "Resource": "arn:aws:s3:::bucket/*",
            "Condition" : {
                "IpAddress" : {
                    "aws:SourceIp": "10.10.10.0/24" 
                },
                "NotIpAddress" : {
                    "aws:SourceIp": "10.10.10.100/32" 
                } 
            } 
        } 
    ]
}
```

Allow anyone in the 10.10.10.0/24 network except for 10.10.10.100/32.