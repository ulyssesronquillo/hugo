---
title: 'aws cli ec2 impaired instances'
author: ulysses

date: 2019-07-22
slug: aws-cli-ec2-impaired-instances
draft: false
---

Here’s how to get a list of EC2 instances with a status of impaired.

```
aws ec2 describe-instance-status \
--filters Name=instance-status.status,Values=impaired
```