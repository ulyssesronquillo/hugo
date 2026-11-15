---
title: 'aws s3 acceleration cli'
author: ulysses

date: 2020-10-04
slug: aws-s3-acceleration-cli
draft: false
---

Here is how to enable Amazon S3 Transfer Acceleration on a S3 bucket.

```
aws s3api put-bucket-accelerate-configuration \
--bucket bucketname \
--accelerate-configuration Status=Enabled \
--region us-east-1
```

Use an accelerate endpoint.

```
aws configure set default.s3.use_accelerate_endpoint true
```

To copy files to S3 you can use the default copy.

```
aws s3 cp file.txt s3://bucketname/keyname \
--region us-east-1
```

Or use the acceleration endpoint.

```
aws configure set s3.addressing_style virtual
aws s3 cp file.txt s3://bucketname/keyname \
--endpoint-url http://s3-accelerate.amazonaws.com \
--region us-east-1
```