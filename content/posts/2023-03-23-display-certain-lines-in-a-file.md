---
title: 'display certain lines in a file'
author: ulysses

date: 2023-03-23
slug: display-certain-lines-in-a-file
draft: false
---

This will display only lines 40-50 in a file called lines.txt.

```
$ cat lines.txt | head -n 50 | tail -n 10
```

For lines 90-100.

```
$ cat lines.txt | head -n 100 | tail -n 10
```

and so on.