---
title: 'migrate efs to another vpc'
author: ulysses

date: 2019-07-21
slug: migrate-efs-to-another-vpc
draft: false
---

Migrating a EFS from one VPC to another is quite simple. There’s no need to delete it. Just click on “manage file systems access” and remove all mount targets and Save. Once the targets are removed, you can choose another VPC from the dropdown. Once a VPC is selected. Add the subnets and security groups. Save and you are done!

![](https://uly.me/wp-content/uploads/2019/07/efs-vpc.png)