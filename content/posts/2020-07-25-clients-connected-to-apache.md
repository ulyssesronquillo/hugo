---
title: 'clients connected to apache'
author: ulysses

date: 2020-07-25
slug: clients-connected-to-apache
draft: false
---

Here’s how to find if clients are connected to Apache or Nginx service.

```
netstat -tn src: 80
netstat -tn src: 443
```