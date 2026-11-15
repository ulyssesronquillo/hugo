---
title: 'python read file multiple columns'
author: ulysses

date: 2023-06-26
slug: python-read-file-multiple-columns
draft: false
---

Here’s how to read a file line by line with multiple columns.

```
with open('file.txt') as file:
    for line in file:
        line = line.strip()
        columns = line.split()
        col1 = columns[0]
        col2 = columns[1]
        some_function(col1, col2) 
```