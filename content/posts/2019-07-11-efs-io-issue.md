---
title: 'efs io issue'
author: ulysses

date: 2019-07-11
slug: efs-io-issue
draft: false
---

If the EFS mount is unresponsive, try using this …

```
/bin/ls -1f
```

This is an issue with having too many small files in a directory. This can be fixed by sharding files to multiple sub-directories.