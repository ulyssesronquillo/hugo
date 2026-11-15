---
title: 'aws ec2 ena support'
author: ulysses

date: 2021-05-07
slug: aws-ec2-ena-support
draft: false
---

AWS has machine types that require ENA Support. You can run AWS CLI to find out if instance is ENA enabled.

```
aws ec2 describe-instances \
--instance-id i-xxxxxxxxxxxxxxxxx \
--profile default \
--region us-east-1 \
--query 'Reservations[].Instances[].EnaSupport'
```

Login to the instance and verify.

```
sudo lspci | grep -i Amazon
```

List driver details.

```
modinfo nvme
```

Verify modules loaded at startup.

```
lsmod | grep nvme
lsmod | grep ena
```

If ENA drivers are missing, install them.

```
yum install pciutils
```