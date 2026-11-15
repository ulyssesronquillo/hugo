---
title: 'check argument in bash'
author: ulysses

date: 2019-01-15
slug: check-argument-in-bash
draft: false
---

How to check for an argument in a script in Bash.

```
if [ -z "$1" ] ; then
  echo "there are no arguments"
else
  echo "there is an argument"
fi
```