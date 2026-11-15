---
title: 'xfs vs ext4 commands'
author: ulysses

date: 2019-04-30
slug: xfs-vs-ext4-commands
draft: false
---

File system command differences between ext3 and xfs.

| Task | ext4 | xfs |
|---|---|---|
| Creating a file system | mkfs.ext4 | mkfs.xfs |
| Mounting a file system | mount | mount |
| Resizing a file system | resize2fs | xfs\_growfs |
| Repairing a file system | e2fsck | xfs\_repair |
| Changing the label on a file system | e2label | xfs\_admin -L |
| Reporting on disk space and file usage | quota | quota |
| Debugging a file system | debugfs | xfs\_db |
| Saving critical file system metadata to a file | e2image | xfs\_metadump |

<div style="clear:both"></div>