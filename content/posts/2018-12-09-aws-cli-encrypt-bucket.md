---
title: 'aws cli encrypt bucket'
author: ulysses

date: 2018-12-09
slug: aws-cli-encrypt-bucket
draft: false
---

Here’s the CLI command to set server-side AES-256 encryption on a bucket.

```
$ aws s3api put-bucket-encryption --bucket bucket-name \
--server-side-encryption-configuration \
'{"Rules": [{"ApplyServerSideEncryptionByDefault": {"SSEAlgorithm": "AES256"}}]}'
```

You can apply this to any existing bucket.