---
title: 'aws cli contains'
author: ulysses

date: 2021-01-16
slug: aws-cli-contains
draft: false
---

The AWS CLI has a not so well-known comparison operator called “contains” which can be used to filter or query the output of your results. In this example, we want to show only instances that were not terminated.

Here’s a query containing “?!contains().”

```
aws ec2 describe-instances \
--query 'Reservations[*].Instances[?!contains(State.Name, `terminated`)].{Instance:InstanceId}'
--output text
```