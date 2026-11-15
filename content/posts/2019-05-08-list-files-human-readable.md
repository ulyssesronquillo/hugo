---
title: 'list files human readable'
author: ulysses

date: 2019-05-08
slug: list-files-human-readable
draft: false
---

How to list files that’s human readable in GB.

```
ls -lrt --block-size=G
```

- l = long format
- t = sort time/date
- r = reverse order
- –block-size=M (Mb) or G (Gb)