---
title: 'attach an ebs volume to an instance'
author: ulysses

date: 2018-10-10
slug: attach-an-ebs-volume-to-an-instance
draft: false
---

Attaching an EBS volume to an existing instance is quite easy. You can easily add them via the AWS Console. With just a few clicks, you can add an EBS volume in no time. Just click the Create Volume button, indicate the size of the volume, choose which availability zone (preferably the same AZ where your instance resides), and enable encryption if you decide to do so. You can also add an EBS volume from an existing snapshot.

There are 2 steps to attaching an EBS volume to an existing instance.

Step 1. Attach an EBS volume.

[How to attach an EBS to an existing Instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-attaching-volume.html).

Step 2. Make the EBS volume available to your instance whether it’s Linux or Windows. This requires SSH access.

[Making an EBS volume available to Linux](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-using-volumes.html).  
[Making an EBS volume available to Windows](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ebs-using-volumes.html).