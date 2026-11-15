---
title: 'leading zeros for numbers below 10'
author: ulysses

date: 2023-08-16
slug: leading-zeros-for-numbers-below-10
draft: false
---

When displaying in a time format, it’s best to display numbers below 10 with leading zeros.

Here’s a nice function you can call to covert numbers below 10.

```
convert ()
{
    # print the number as a string with a leading zero
    number=$(printf '%02d\n' "$1")
    echo $number
}
convert 5
```

Result

```
05
```