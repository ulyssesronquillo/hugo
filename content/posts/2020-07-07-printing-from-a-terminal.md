---
title: 'printing from a terminal'
author: ulysses

date: 2020-07-07
slug: printing-from-a-terminal
draft: false
---

There are times you just want to print directly from the command line.

```
# check your printing options
lpotions
lpinfo -v
# what's your default printer
lpinfo -p -d
# use lp to print
lp notes.txt
# use -n print multiple copies
lp -n 2 notes.txt
# check the printer queue
lp -q
# use the job number to cancel print jobs if needed
cancel 123
```