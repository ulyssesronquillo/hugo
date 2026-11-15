---
title: 'count string characters'
author: ulysses

date: 2021-03-03
slug: count-string-characters
draft: false
---

Here’s a simple little script that displays the number of characters in a string.

```
#!/bin/bash
if [[ $# -eq 0 ]] ; then echo 'Missing arguments'; exit 0; fi
var=$1
size=${#var}
echo $size
```

Command:

```
./length.sh abcdefghijklmnopqrstuvwxyz
```

Output:

```
26
```