---
title: 'tail a file in windows server'
author: ulysses

date: 2019-11-19
slug: tail-a-file-in-windows-server
draft: false
---

Linux has tail command. What about Windows? You can use Powershell to tail a file.

```
Get-Content myLog.log –Wait
```