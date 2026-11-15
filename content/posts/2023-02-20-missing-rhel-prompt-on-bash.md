---
title: 'missing rhel prompt on bash'
author: ulysses

date: 2023-02-20
slug: missing-rhel-prompt-on-bash
draft: false
---

Here’s how to restore or set the Bash prompt on RHEL systems.

```
echo "PS1='\u@\h \w]\$'" >> ~/.bashrc
source ~/.bashrc
```