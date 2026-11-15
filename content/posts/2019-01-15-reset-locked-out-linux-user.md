---
title: 'reset locked out linux user'
author: ulysses

date: 2019-01-15
slug: reset-locked-out-linux-user
draft: false
---

Perform this command to reset a Linux account that has been locked out due to multiple login failures. This involves resetting the pam\_tally back down to zero. Some systems use pam\_tally2. First, check what’s the current tally.

Current tally:

```
pam_tally --user=username
pam_tally2 --user=username
```

To reset:

```
pam_tally --user=username --reset
pam_tally2 --user=username --reset
```