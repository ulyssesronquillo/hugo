---
title: 'add date to filenames'
author: ulysses

date: 2019-06-23
slug: add-date-to-filenames
draft: false
---

Here’s how to add date stamps to filenames. Uses epoch time.

```
tar cpzf mybackup-`date +%s`.gz /home/user
```