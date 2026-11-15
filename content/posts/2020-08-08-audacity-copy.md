---
title: 'audacity copy'
author: ulysses

date: 2020-08-08
slug: audacity-copy
draft: false
---

I was getting an error when launching Audacity.

The error was:

> “The system has detected that another copy of Audacity is running.”

However, Audacity wasn’t running at all. Not one process. It turned out to be just a locked file located in /var/tmp/audacity-\[your-username\].

All you have to do is delete the entire directory and rerun Audacity.

```
rm -rf /var/tmp/audacity=[your-username]/
```

Once deleted, Audacity starts right up with no issues.