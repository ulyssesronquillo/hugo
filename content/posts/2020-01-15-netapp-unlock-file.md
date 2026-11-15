---
title: 'netapp unlock file'
author: ulysses

date: 2020-01-15
slug: netapp-unlock-file
draft: false
---

To get status of a file.

```
lock status -f "/vol/folder/path/filename.doc" -p cifs
```

To unlock a file.

```
lock break -f "/vol/folder/path/filename.doc" -p cifs
```