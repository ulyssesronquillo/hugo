---
title: 'aws cli: describe instances'
author: ulysses

date: 2018-12-13
slug: aws-cli-describe-instances
draft: false
---

If you have a ton of EC2 instances, one way to get results quickly is to run to use AWS CLI such as “describe-instances.” Here’s an example on how to get a list of instances with a tag name equal to some value. In addition, you limit the display only results you want displayed.

```
$ aws ec2 describe-instances \
--query 'Reservations[].Instances[].Tags[?Key==`Name`].Value' \
--filter Name=tag:Project,Values=web \
--region us-east-1 \
--profile default \
--output text
```

This returns values of the “Name” tag name in instances where they occur.