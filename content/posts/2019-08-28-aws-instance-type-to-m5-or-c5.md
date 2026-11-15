---
title: 'aws instance type to m5 or c5'
author: ulysses

date: 2019-08-28
slug: aws-instance-type-to-m5-or-c5
draft: false
---

If you have changed instance type to either C5 or M5 and it no longer boots, it’s due to the following reasons.

1. The Elastic Network Adapter (ENA) enaSupport attribute is disabled for the instance.
2. The ENA module isn’t installed on the instance
3. The NVMe module isn’t installed on the instance, or, if installed, the NVMe module isn’t loaded in the initramfs image of the instance.
4. You are trying to mount the file systems at boot time in the “/etc/fstab” file using a device name. Amazon Elastic Block Store (Amazon EBS) volumes are exposed as NVMe devices to these instance types, and the device names are changed. To avoid this, mount the file systems using UUID/Label. For more information, see [Amazon EBS and NVMe](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/nvme-ebs-volumes.html).

You will need to run a Bash script to update the current instance to be able to support a [C5 or M5](https://aws.amazon.com/premiumsupport/knowledge-center/boot-error-linux-m5-c5/) instance.