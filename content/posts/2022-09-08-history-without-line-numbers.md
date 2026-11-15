---
title: 'history without line numbers'
author: ulysses

date: 2022-09-08
slug: history-without-line-numbers
draft: false
---

Here’s how to display history without the line numbers.

```
history -w /dev/stdout
```

Result

```
cd /etc/httpd/conf
view httpd.conf 
vim wiki.conf 
vim ssl.conf
```