---
title: 'aws security groups ip cidr'
author: ulysses

date: 2019-09-10
slug: aws-security-groups-ip-cidr
draft: false
---

Here’s how to search for AWS Security Groups containing this IP Cidr.

```
aws ec2 describe-security-groups \
--filter Name=egress.ip-permission.cidr,Values='10.8.8.8/32' \
--query "SecurityGroups[*].{Name:GroupName}" \
--output text \
--profile default \
--region us-east-1 
```

Search with ports.

```
aws ec2 describe-security-groups \
--filter Name=egress.ip-permission.cidr,Values='10.8.8.8/32' \
         Name=egress.ip-permission.from-port,Values='22' \
         Name=egress.ip-permission.to-port,Values='22' \
--query "SecurityGroups[*].{Name:GroupName}" \
--output text \
--profile default \
--region us-east-1 
```

Query will only display the Security Group name.