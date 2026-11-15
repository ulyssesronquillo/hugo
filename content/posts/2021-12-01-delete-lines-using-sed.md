---
title: 'delete lines using sed'
author: ulysses

date: 2021-12-01
slug: delete-lines-using-sed
draft: false
---

How to delete a line containing a pattern using sed.

Contents of test.txt.

```
$ cat test.txt
one
two
three
```

Delete a line matching the string “one.”

```
sed -i '/one/d' test.txt
```

Display test.txt

```
$ cat test.txt
two
three
```