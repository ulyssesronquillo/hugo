---
title: 'install boto3 aws sdk for python'
author: ulysses

date: 2017-05-18
slug: install-boto3-aws-sdk-for-python
draft: false
---

Boto3 is the Amazon Web Services (AWS) SDK for Python, which allows Python developers to write software that makes use of Amazon services like S3 and EC2. Boto provides an easy to use, object-oriented API as well as low-level direct service access.

To install on Mac

```
sudo easy_install pip
sudo pip install —ignore-installed six boto3
```

You need to set up your credentials and config file to authenticate to AWS first. The files are:

.aws/credentials  
.aws/config

After it’s installed and configured, try using Boto3 to fetch your AWS S3 buckets.

```
import boto3
s3 = boto3.resource('s3')
for bucket in s3.buckets.all():
  print(bucket.name)
```

Your S3 buckets will be listed after execution.

Boto3 has access to other AWS resources like EC2, meaning you can start and stop instances via Python and Boto3.