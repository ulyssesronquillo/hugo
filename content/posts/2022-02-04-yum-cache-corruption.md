---
title: 'yum cache corruption'
author: ulysses

date: 2022-02-04
slug: yum-cache-corruption
draft: false
---

If you’re getting a “HTTP Error 404 – Not Found” error when trying to run yum update, it could be a corrupted cache. Clear the cache on the system by running the following.

```
yum clean all
rm -rf /var/cache/yum/*
```

Run yum update again. The errors should be gone.