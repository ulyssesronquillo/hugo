---
title: 'could not empty the trash can'
author: ulysses

date: 2016-11-09
slug: cant-empty-the-trash-can
draft: false
---

If you have trouble emptying the trash this morning, here’s a helpful tip.

Your OS is essentially telling you the file is in use, but the application is close.

Nothing like running rm -rf on the trash folder.

```
# Go the trash directory and delete all!
cd ~/.Trash
rm -rf *
```

The file is gone!