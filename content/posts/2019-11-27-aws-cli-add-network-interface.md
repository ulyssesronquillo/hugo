---
title: 'aws cli add network interface'
author: ulysses

date: 2019-11-27
slug: aws-cli-add-network-interface
draft: false
---

Create a new interface via AWS CLI with static IP.

```
$ aws ec2 create-network-interface \
--subnet-id subnet-xxxxxxx \
--description "second ip" \
--groups sg-xxxxxxx \
--private-ip-address 10.0.0.16
```