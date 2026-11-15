---
title: 'random salt'
author: ulysses

date: 2018-05-09
slug: random-salt
draft: false
---

Occasionally, I’m asked to provide a random list of characters that will be used as a salt for hashing a password or some data of some sort. The primary function of salts are to create a random one-way function typically used to fight against dictionary or rainbow table attacks. Here’s a neat command that you can generate from the Bash shell. It will generate a 32 random character string.

```
$ tr -c -d '0123456789abcdefghijklmnopqrstuvwxyz' /urandom | dd bs=32 count=1 2>/dev/null;echo
```

The result is: ynhgunq3ppnirhhp3vxpmvdw5b2uuc2f