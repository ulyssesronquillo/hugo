---
title: 'aws cli restore object from s3 glacier'
author: ulysses

date: 2019-06-26
slug: aws-cli-restore-object-from-s3-glacier
draft: false
---

How to restore an object from Amazon S3 Glacier via the AWS CLI.

```
aws s3api restore-object \
--bucket awsexamplebucket \
--key dir1/example.obj \
--restore-request '{"Days":25,"GlacierJobParameters":{"Tier":"Standard"}}'
```