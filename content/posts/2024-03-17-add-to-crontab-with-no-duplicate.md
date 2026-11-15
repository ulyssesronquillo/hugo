---
author: ulysses
title: 'add to crontab with no duplicate'
date: 2024-03-17
slug: add-to-crontab-with-no-duplicate
draft: false
---

How to add to a crontab without creating duplicates. 

```
crontab -l | grep 'myscript.sh' || (crontab -l 2>/dev/null; echo "45 10 * * * /path/to/myscript.sh") | crontab -
```

