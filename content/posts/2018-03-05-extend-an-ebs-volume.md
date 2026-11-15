---
title: 'extend an ebs volume'
author: ulysses

date: 2018-03-05
slug: extend-an-ebs-volume
draft: false
---

As a Cloud Engineer, I get a few requests to extend an EBS volume. For example, the application owner wants to double the size of the /data volume from 10GB to 20GB. The nice part about extending an EBS volume is that it can all be done on the fly without bringing down the instance. Adding more storage can be done via the AWS Console. Check out this [article](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/console-modify.html) from AWS about modifying an EBS volume. But that’s just the first part. Although you’ve doubled the disk space, you still have to let the system know it now has doubled it’s disk space. The second part is to grow or resize the file system. Here’s the other [article](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/recognize-expanded-volume-linux.html) on how to extend a file system.

```
# expand
growpart /dev/xvdb
# for ext2, ext3 and ext4
resize2fs /dev/xvdb
# for xfs
xfs_growfs -d /dev/xvdb
```