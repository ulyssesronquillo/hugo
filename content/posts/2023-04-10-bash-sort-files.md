---
title: 'bash sort files'
author: ulysses

date: 2023-04-10
slug: bash-sort-files
draft: false
---

How to sort files in Bash.

Display contents

```
$ cat file.txt
bbb
aaa
ccc
kkk
uuu
ppp
```

Sort

```
$ sort file.txt
aaa
bbb
ccc
kkk
ppp
uuu
```

Sort in place

```
$ sort -o file.txt file.txt
$ cat file.txt
aaa
bbb
ccc
kkk
ppp
uuu
```