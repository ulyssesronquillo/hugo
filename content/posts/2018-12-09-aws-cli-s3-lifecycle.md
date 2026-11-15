---
title: 'aws cli s3 lifecycle'
author: ulysses

date: 2018-12-09
slug: aws-cli-s3-lifecycle
draft: false
---

Here’s how to add a lifecycle management to S3 buckets via the CLI. In this example, expiration is set to 7 days. S3 will auto delete expired objects.

```
$aws s3api put-bucket-lifecycle-configuration \
--bucket bucketname --lifecycle-configuration file://lifecycle.json
```

The lifecycle is defined in this JSON file.

```
{
  "Rules": [ 
    {
       "ID": "Expires in 7 DAYS", 
       "Prefix": "", 
       "Status": "Enabled", 
       "Expiration": { 
         "Days": 7
         }
    } 
  ] 
}
```