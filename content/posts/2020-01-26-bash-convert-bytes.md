---
title: 'bash convert bytes'
author: ulysses

date: 2020-01-26
slug: bash-convert-bytes
draft: false
---

Here’s a function to convert bytes into kilo, mega, giga, tera up to zeta bytes.

```
function convert_bytes {
    bytes=$credits
    b=${bytes:-0}; d=''; s=0; S=(Bytes {K,M,G,T,E,P,Y,Z}B)
    while ((b > 1024)); do
        d="$(printf ".%02d" $((b % 1000 * 100 / 1000)))"
        b=$((b / 1000))
        let s++
    done
    echo "$b$d ${S[$s]}"
}
credits=2308974418330
echo $credits 
convert_bytes $credits
```

Result is:

```
2308974418330
2.30 TB
```