---
title: 'bash read file'
author: ulysses

date: 2021-12-01
slug: bash-read-file
draft: false
---

How to read a file line by line in Bash.

```
#!/bin/bash
file=test.txt
while IFS= read -r line; do
  echo $line
done
```

Contents of test.txt.

```
one
two
three
```

Results when running test.sh.

```
$ bash test.sh
one
two
three
```

To read multiple strings line by line.

```
#!/bin/bash
file=test.txt
while read -r a b; do
  echo $b
done 
```

Modified contents of test.txt.

```
one 1
two 2
three 3
```

New results.

```
$ bash test.sh
1
2
3
```