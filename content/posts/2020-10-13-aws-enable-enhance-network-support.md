---
title: 'aws enable enhance network support'
author: ulysses

date: 2020-10-13
slug: aws-enable-enhance-network-support
draft: false
---

When changing machine types, you may be asked to enable the latest ENA driver for Enhanced Network Support on an Amazon EC2 instance. There are several instructions depending on the Linux OS flavor. Here are the instructions to [enable](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/enhanced-networking-ena.html#enhanced-networking-ena-linux). In some cases, you may need to [rebuild the kernel module](https://aws.amazon.com/premiumsupport/knowledge-center/install-ena-driver-rhel-ec2/). To verify that the ena module is installed, use the modinfo command as shown in the following example.

```
modinfo ena
```

You also may have to enable the enhanced networking attribute on the instance.

```
aws ec2 modify-instance-attribute --instance-id instance_id --ena-support
```