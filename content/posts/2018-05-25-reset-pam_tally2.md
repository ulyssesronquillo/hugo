---
title: 'reset pam_tally2'
author: ulysses

date: 2018-05-25
slug: reset-pam_tally2
draft: false
---

To unlock a locked account, you need to run pam\_tally2, which is a tool that keeps tracked of failed logins. Pam\_tally2 is installed on most Linux systems. To unlock an account, just run the following commands:

```
pam_tally2 --user=ulysses --reset
```

Have the user login again. It should work.

Some systems might be using an older pam\_tally. The command for that will be.

```
pam_tally --user=ulysses --reset=0
```