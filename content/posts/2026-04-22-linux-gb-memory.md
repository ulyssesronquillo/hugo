---
author: ulysses
title: 'linux gb memory'
date: 2026-04-22
slug: linux-gb-memory
draft: false
---
This is the command to display system memory in GB in Linux.

```
grep -E 'MemTotal|MemAvailable' /proc/meminfo | awk '{printf "%s %.2f GB\n", $1, $2/1024^2}'
```

