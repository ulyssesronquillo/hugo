---
title: 'aws cli ec2 instance status'
author: ulysses

date: 2019-07-17
slug: aws-cli-ec2-instance-status
draft: false
---

How to display AWS EC2 instance statuses.

```
aws ec2 describe-instance-status \
--query 'InstanceStatuses[].[InstanceId,SystemStatus.Status]' \
--include-all-instances \
--region us-east-2
--profile abcdef \
```

Query and Filter.

```
aws ec2 describe-instance-status \
--query 'InstanceStatuses[].[InstanceId,SystemStatus.Status]' \
--filter 'Name=instance-state-name,Values=stopped' \
--region us-east-2
--profile abcdef \
```

Filter event.code equal to instance-reboot.

```
aws ec2 describe-instance-status \
--query 'InstanceStatuses[].[InstanceId,SystemStatus.Status]' \
--filter 'Name=eventcode,Values=instance-reboot' \
--region us-east-2
--profile abcdef \
```