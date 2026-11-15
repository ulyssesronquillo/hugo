---
title: 'running top by process'
author: ulysses

date: 2022-09-11
slug: running-top-by-process
draft: false
---

Here’s how to isolate a process via the top command.

```
top -c -p $(pgrep -f process_name | head -20 | tr "\\n" "," | sed 's/,$//')
```