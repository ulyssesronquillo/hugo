---
title: 'bash history with timestamps'
author: ulysses

date: 2019-10-31
slug: bash-history-with-timestamps
draft: false
---

If you need to see Bash history with timestamps, use this command.

```
HISTTIMEFORMAT="%d/%m/%y %T "
```

To make it permanent, add it to your .bashrc.

```
echo 'HISTTIMEFORMAT="%d/%m/%y %T "' >> ~/.bashrc
source ~/.bashrc
```

Timestamps accuracy is retroactively, meaning it will not be accurate for commands performed prior to the history time format being set.