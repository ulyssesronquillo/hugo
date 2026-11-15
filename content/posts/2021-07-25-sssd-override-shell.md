---
title: 'sssd override shell'
author: ulysses

date: 2021-07-25
slug: sssd-override-shell
draft: false
---

If you have SSSD running and the default shell is ksh even with the default shell set to bash.

Here’s the fix to override the default shell in /etc/sssd/sssd.conf. Add override\_shell.

```
default_shell = /bin/bash
override_shell = /bin/bash
```

To check which shell you are using.

```
echo $SHELL
/bin/bash
```