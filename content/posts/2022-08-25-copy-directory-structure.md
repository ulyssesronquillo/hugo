---
title: 'copy directory structure'
author: ulysses

date: 2022-08-25
slug: copy-directory-structure
draft: false
---

Here’s how to copy a directory structure from one directory to another without the files.

Copy directory structure of DIR1 to DIR2.

```
find /DIR1 -type d > /tmp/dirs.txt
sed -i 's/DIR1/DIR2/' /tmp/dirs.txt 
xargs mkdir -p 
```