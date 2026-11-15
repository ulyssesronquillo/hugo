---
title: 'aws cli ec2 describe tags'
author: ulysses

date: 2019-08-26
slug: aws-cli-ec2-describe-tags
draft: false
---

Here’s how to get a list of EC2 tags.

```
aws ec2 describe-tags \
--filters "Name=resource-id,Values=i-xxxxxxxxxxxxx" \
--query 'Tags[][Key,Value]'  \
--profile default \
--region us-east-1 \
--output text
```