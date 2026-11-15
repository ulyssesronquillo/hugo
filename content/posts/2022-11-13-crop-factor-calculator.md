---
title: 'crop factor calculator'
author: ulysses

date: 2022-11-13
slug: crop-factor-calculator
draft: false
---

If you’re into photography, you would know what crop factor means. I have a Nikon D90 camera with a crop factor of 1.5. For example, if you use a 24mm full frame lens on a D90, the focal length will be 36mm. So, here’s a handy bash script that calculates the crop factor by multiplying the full frame focal length by 1.5.

```
#!/bin/bash
if [ $# -eq 0 ]
  then
    echo "Usage: cropfactor.sh 24"
    exit
fi
a=$(echo "1.5 * $1" | bc)
echo "Cropfactor focal length is: " $a"mm."
```

Result

```
ulysses@penguin:~/Code$ ./cropfactor.sh 24
Cropfactor focal length is:  36.0mm.
```