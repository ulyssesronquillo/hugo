---
title: 'bash replace spaces with a comma'
author: ulysses

date: 2023-05-08
slug: bash-replace-spaces-with-a-comma
draft: false
---

Replace spaces with commas from one file and send the output to another file.

```
tr -s '[:blank:]' ', '  output.txt
```

It’s perfect for creating a comma delimited file for importing to Excel.