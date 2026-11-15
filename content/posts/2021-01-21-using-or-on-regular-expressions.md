---
title: 'using or on regular expressions'
author: ulysses

date: 2021-01-21
slug: using-or-on-regular-expressions
draft: false
---

Here’s a regex using the pipe symbol as OR to allow only 6 possible values.

```
regex="efs-(00|04|08|12|16|20)00"
```

Matches:

```
efs-0000
efs-0400
efs-0800
efs-1200
efs-1600
efs-2000
```

No matches:

```
efs-0100
efs-2200
efs-0600
efs-1400
efs-1800
efs-1110
111022
asdb023
2330asd
1200-efs
1205
abc
```

$var is compared with $regex to find a match. $var is any of the variables above.

```
if [[ $var != $regex ]]; then
  echo "Not a match"
else
  echo "It's a match"
fi
```