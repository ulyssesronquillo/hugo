---
title: 'aws cli create bucket'
author: ulysses

date: 2018-12-09
slug: aws-cli-create-bucket
draft: false
---

Creating a bucket via the AWS Console takes only a few clicks. If you’re creating a bucket via shell script, you will need to use the AWS CLI (command line interface). So, here’s the script to create a S3 bucket via the AWS CLI within shell. Now the bucket name has to be globally unique similar to a domain name. If someone already has claimed it, you will need to use an alternative name.

```
aws s3api create-bucket --bucket bucket-name --region us-east-2 create-bucket-configuration LocationConstraint=us-east-2
```