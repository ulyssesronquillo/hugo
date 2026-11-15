---
title: 'replace spaces with comma'
author: ulysses

date: 2020-02-04
slug: replace-spaces-with-comma
draft: false
---

Here’s a simple sed command to replace multiple spaces into a comma delimited file.

sample.txt

```
one       two
three     four
```

The sed command.

```
sed 's/ \+ /,/g' sample.txt > sample2.txt
```

sample2.txt

```
one,two
three,four
```