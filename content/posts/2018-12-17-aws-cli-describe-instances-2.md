---
title: 'aws cli describe instances'
author: ulysses

date: 2018-12-17
slug: aws-cli-describe-instances-2
draft: false
---

If you have the instance id, you can print out the details like this:

```
aws ec2 describe-instances --instance-ids i-xxxxxxxxxxxxx \
--region us-east-1 --profile default
```