---
title: 'moving linux directory'
author: ulysses

date: 2019-06-17
slug: moving-linux-directory
draft: false
---

Moving a Linux directory the safe way.

```
cd /mydir ; tar cf - . | (cd /data/mydir ; tar xf -) ; mv /mydir /mydir.0 ; ln -s /data/mydir /mydir
```