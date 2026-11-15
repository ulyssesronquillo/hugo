---
title: 'bash reformat numbers'
author: ulysses

date: 2022-02-27
slug: bash-reformat-numbers
draft: false
---

How to reformat numbers in Bash.

```
$ n=1023555
$ m=$(numfmt --to=si n)
$ echo $m
1.1M
```

Other options

```
--to=none     # no scaling. Output: 1023555
--to=si       # International System of Units (SI) standard. Output 1.1M
--to=iec      # International Electrotechnical Commission (IEC) standard. Output: 1.1Mi 
--to=iec-i    # International Electrotechnical Commission (IEC) standard. Output: 1.1M
--to=auto     # ‘auto’ can only be used with --from.
```

[fmtnum](http://www.gnu.org/software/coreutils/manual/html_node/numfmt-invocation.html)