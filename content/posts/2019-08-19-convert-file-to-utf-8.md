---
title: 'convert file to utf-8'
author: ulysses

date: 2019-08-19
slug: convert-file-to-utf-8
draft: false
---

Here’s how to convert multiple files to UTF-8 format.

```
for file in *.csv; do
    iconv -f ascii -t utf-8 "$file" -o "${file%.txt}.utf8.csv"
done
```