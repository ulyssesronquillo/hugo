---
title: 'bash split a string with delimiter'
author: ulysses

date: 2023-09-18
slug: bash-split-a-string-with-delimiter
draft: false
---

Here’s how to split a string that contains a delimeter.

String

```
server-boot;server-data
```

Split the string and print on every line.

```
data="server-boot;server-data"
for i in $(echo $data | tr ";" "\n"); do
  echo $i
done
```

Result

```
server-boot
server-data
```

Send output to a file

```
file="output.txt"
> $file
data="server-boot;server-data"
for i in $(echo $data | tr ";" "\n"); do
  echo $i >> $file
done
```