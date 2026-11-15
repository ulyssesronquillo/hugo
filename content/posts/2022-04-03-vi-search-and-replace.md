---
title: 'vi search and replace'
author: ulysses

date: 2022-04-03
slug: vi-search-and-replace
draft: false
---

How to do search and replace in Vim.

Search for “foo” and replace it with “bar” in the current line. Use :s

```
:s/foo/bar/g
```

Search for “foo” and replace it with “bar” in the entire document. Use :%s

```
:%s/foo/bar/g
```

You can also pipe instead of forward slash. Useful if your search contains a /.

```
:%s|foo/|bar|g
```