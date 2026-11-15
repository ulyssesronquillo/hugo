---
title: 'aws cli bucket lifecycle configuration'
author: ulysses

date: 2018-12-14
slug: aws-cli-bucket-lifecycle-configuration
draft: false
---

I was banging my head against the wall (not quite literally, but it was close) trying to come up with a S3 lifecycle configuration from scratch. I needed a JSON file that I can run in a bash script, so I can apply the lifecycle rules to a few dozen S3 buckets. Obviously, trying to create one from scratch wasn’t the wisest choice in my part. As it turns out, you can setup a temporary bucket and use the console to recreate the lifecycle, then export the lifecycle JSON file. Duh! Genius! Here’s the command to export the lifecycle configuration.

```
aws s3api get-bucket-lifecycle-configuration \
--bucket bucket-name
```

The output would be in a JSON format similar to this:

```
{
    "Rules": [
        {
            "Status": "Enabled",
            "NoncurrentVersionExpiration": {
                "NoncurrentDays": 90
            },
            "NoncurrentVersionTransitions": [
                {
                    "NoncurrentDays": 7,
                    "StorageClass": "INTELLIGENT_TIERING"
                }
            ],
            "Filter": {
                "Prefix": ""
            },
            "Expiration": {
                "ExpiredObjectDeleteMarker": true
            },
            "AbortIncompleteMultipartUpload": {
                "DaysAfterInitiation": 7
            },
            "ID": "EFS S3 Backup Lifecycle Rules"
        }
    ]
}
```