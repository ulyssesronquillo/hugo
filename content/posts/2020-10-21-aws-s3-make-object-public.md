---
title: 'aws s3 make object public'
author: ulysses

date: 2020-10-21
slug: aws-s3-make-object-public
draft: false
---

Copy object or file to S3 bucket.

```
aws s3 cp filename.ext s3://bucketname/ --profile your-profile
```

To make it publicly available, run this command.

```
aws s3api put-object-acl \
--bucket bucket-name \
--key filename.ext \
--acl public-read \
--profile your-profile
```