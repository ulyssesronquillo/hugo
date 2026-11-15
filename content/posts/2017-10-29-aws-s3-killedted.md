---
title: 'aws s3 killedted'
author: ulysses

date: 2017-10-29
slug: aws-s3-killedted
draft: false
---

I was trying to copy a large file from AWS S3 bucket to the smallest Amazon Lightsail instance using the AWS CLI. It was throwing out an error saying “Killedted 3.8 Mib/113.4 Mib (5.0 Mib/s) with 1 file(s) remaining.” For some reason, the copy was being killed or terminated. I was thinking that maybe the small instance was not enough to copy or move large files. I’m glad I found a [workaround](https://github.com/aws/aws-cli/issues/1775). Here’s the command I was doing, and the fix.

The Error

```
$ aws s3 cp s3://bucketname/directory/largefile.mp4 largefile.mp4
$ Killedted 3.8 MiB/113.4 MiB (5.0 MiB/s) with 1 file(s) remaining
```

The Fix

```
$ aws configure set default.s3.max_concurrent_requests 4
```

The default is 10 which was too much for a small instance.