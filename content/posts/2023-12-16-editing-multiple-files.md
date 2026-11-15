---
author: ulysses
title: 'editing multiple files'
date: 2023-12-16
slug: editing-multiple-files
draft: false
---

Editing 1000+ files is not fun. Here's a script that cycles through certain files in a directory and performs a search and replace.

```
#!/bin/bash
for filename in 20*.md; do
  sed -i -e 's/author: Ulysses/author: ulysses/g' $filename
done
```

In this particular script, it looks for files starting with 20 with an extension of .md. 

The script uses the **sed command** to perform search and replace.
