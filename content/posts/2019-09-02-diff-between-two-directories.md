---
title: 'diff between two directories'
author: ulysses

date: 2019-09-02
slug: diff-between-two-directories
draft: false
---

Here’s how to get the differences between two directories using diff.

- -q display only files when they differ
- -r recursive to all sub-directories

```
diff -qr /directory-1 /directory-2
```