---
title: 'rsync only new files'
author: ulysses

date: 2019-09-09
slug: rsync-only-new-files
draft: false
---

Here’s how to sync files between two directories, while copying only new files and ignoring existing files.

```
rsync --ignore-existing -rapzvh /dir1 /dir2 >> /root/rsync.log &
```