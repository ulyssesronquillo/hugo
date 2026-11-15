---
title: 'aws cli s3 versioning'
author: ulysses

date: 2018-12-12
slug: aws-cli-s3-versioning
draft: false
---

To turn on S3 versioning from the AWS CLI, just run the following command:

```
$ aws s3api put-bucket-versioning --bucket mybucket \
----versioning-configuration Status=Enabled
```