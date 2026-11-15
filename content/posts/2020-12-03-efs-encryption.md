---
title: 'efs encryption'
author: ulysses

date: 2020-12-03
slug: efs-encryption
draft: false
---

If you have an existing EFS that’s unencrypted, you can encrypt it be creating a snapshot using AWS Backup, and then restoring the file system to a new EFS with encryption. If you choose to restore in a directory in the same file system, it will not be encrypted. It has to be a new EFS. In addition, you’ll be asked to select which encryption key to use. The default key will work, unless you have your own.

![](https://uly.me/wp-content/uploads/2020/12/efs-encryption.png)