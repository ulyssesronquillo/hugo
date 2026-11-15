---
title: 'apt locked files'
author: ulysses

date: 2021-10-02
slug: apt-locked-files
draft: false
---

If you tried to run apt update and you get this error, try the following.

```
$ apt update
E: Could not get lock /var/lib/dpkg/lock-frontend - open (11: Resource temporarily unavailable) [duplicate]
```

Kill the process.

```
$ sudo killall apt apt-get
```

If that doesn’t work, remove the locked files.

```
$ sudo rm /var/lib/apt/lists/lock
$ sudo rm /var/cache/apt/archives/lock
$ sudo rm /var/lib/dpkg/lock*
```

Run apt update again.