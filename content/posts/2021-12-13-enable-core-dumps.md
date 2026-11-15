---
title: 'enable core dumps'
author: ulysses

date: 2021-12-13
slug: enable-core-dumps
draft: false
---

Core dumps are triggered by kernel when a program crashses. It saves memory to a file.

How to enable core dumps.

```
ulimit -S -c unlimited
```

Enable core dumps permanently. Edit /etc/security/limits.conf. Add the following.

```
* soft core unlimited
```

Disable core dumps.

```
ulimit -S -c 0
```

Disable core dumps permanently. Edit /etc/security/limits.conf. Add the following.

```
* soft core 0
* hard core 0
```