---
title: 'deleting aws security groups'
author: ulysses

date: 2018-07-15
slug: deleting-aws-security-groups
draft: false
---

Every once in a while, you may need to do some cleanup and perform maintenance in AWS. One area where you can do some cleanup is the security groups. To check if security groups are in-used, is by way of the AWS Console. You can filter the security group via Instances. But that is not going to be enough. Security groups are also used in RDS as well as in load balancers. Overall, you have to be extra careful not to delete a security group that’s in-use. Fortunately, AWS will prompt you if you try to delete a security group that is still in-use. It’s a safety feature that can potentially save you from headaches.