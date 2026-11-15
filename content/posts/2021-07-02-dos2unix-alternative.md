---
title: 'dos2unix alternative'
author: ulysses

date: 2021-07-02
slug: dos2unix-alternative
draft: false
---

If you create scripts in Windows, editors sometimes add a carriage return in addition to the line feed.

You can use dos2unix to remove the extra characters. Or you can use sed.

```
sed -i -e 's/\r$//' script.sh
```