---
title: 's3 browser iam assume role'
author: ulysses

date: 2020-04-12
slug: s3-browser-iam-assume-role
draft: false
---

S3 Browser is a free Windows client for accessing AWS S3 buckets. You can access S3 buckets with an interface similar to File Manager. A typical setup requires that you use access and secret keys to connect to the S3 browser. However, if the server is in the cloud, it’s better that use a machine profile with an assume role. The assume role gets temporary credentials until they expire. They are automatically rotated by AWS behind the scenes for you. This is much safer process than storing key credentials in the cloud. The good news is, S3 Browser support IAM assume roles. Here’s the setup instructions to get your [S3 Browser configured](https://s3browser.com/amazon-s3-via-assume-role.aspx) using IAM assume role. Here’s IAM role [explained](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html).