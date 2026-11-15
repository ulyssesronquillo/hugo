---
title: 'xfs filesystem has duplicate uuid'
author: ulysses

date: 2019-10-07
slug: xfs-filesystem-has-duplicate-uuid
draft: false
---

Here’s how to fix a duplicate UUID on a XFS file system.

```
mount -o rw,nouuid /dev/sda1  /data
```

Mounting with nouuid will work, but not after a reboot.

To avoid a duplicate ID, run this command to generate a new UUID.

```
xfs_admin -U generate /dev/sda3
Clearing log and setting UUID
writing all SBs
new UUID = xxxxx-xxxx-xxxx-xxxxxxxxx
```