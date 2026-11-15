---
title: 'memory info on linux'
author: ulysses

date: 2023-03-15
slug: memory-info-on-linux
draft: false
---

Here’s how to view system memory on Linux.

Default display is in kB

```
cat /proc/meminfo
MemTotal:        7492768 kB
MemFree:          427368 kB
MemAvailable:    5424768 kB
```

Display in MB

```
awk '$3=="kB"{$2=$2/1024;$3="MB"} 1' /proc/meminfo | column -t
MemTotal:           7317.16      MB
MemFree:            404.527      MB
MemAvailable:       5285.4       MB
```

Output in GB

```
awk '$3=="kB"{$2=$2/1024^2;$3="GB";} 1' /proc/meminfo | column -t
MemTotal:           7.14566      GB
MemFree:            0.370392     GB
MemAvailable:       5.13733      GB
```