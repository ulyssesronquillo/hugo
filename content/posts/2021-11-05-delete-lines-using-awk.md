---
title: 'delete lines using awk'
author: ulysses

date: 2021-11-05
slug: delete-lines-using-awk
draft: false
---

Here’s how to delete a line from a file using awk.

```
awk '!/Redhat/' sample.txt > sample.tmp && mv sample.tmp sample.txt
```

The command above looks for ‘Redhat’ in a file and removes that line from the file.

You can add the line in the crontab to run at reboot if you like.

```
crontab -e
```

```
@reboot awk '!/Redhat/' sample.txt > sample.tmp && mv sample.tmp sample.txt
```