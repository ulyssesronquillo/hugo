---
title: 'json formatter'
author: ulysses

date: 2022-01-12
slug: json-formatter
draft: false
---

If you have a json file that needs formatting, you can use a built-in tool in Python.

```
python -m json.tool sample.json
```

Output will be printed on screen. You can also send the output to a file.

```
python -m json.tool sample.json > sample2.json
```