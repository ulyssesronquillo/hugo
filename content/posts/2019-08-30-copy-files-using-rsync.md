---
title: 'copy files using rsync'
author: ulysses

date: 2019-08-30
slug: copy-files-using-rsync
draft: false
---

Here’s how to copy files from one directory to another.

```
rsync -arvz /dir1 /dir2 >> /tmp/rsync.log &
```

Format: rsynch –options source destination

Options

- -a archive mode
- -v verbose
- -p keep permissions
- -z zipped during transfer
- -r recursive