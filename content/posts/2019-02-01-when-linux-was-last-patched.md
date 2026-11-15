---
title: 'when linux was last patched'
author: ulysses

date: 2019-02-01
slug: when-linux-was-last-patched
draft: false
---

Here’s a handy command to see if Linux was patched recently.

```
rpm -qa --last | head
```

A typical result would look something like this.

```
name-of-patch          Sun 20 Jan 2019 05:36:31 PM UTC
name-of-patch          Fri 18 Jan 2019 02:52:51 PM UTC
```