---
title: 'elapse time on bash script'
author: ulysses

date: 2019-09-24
slug: elapse-time-on-bash-script
draft: false
---

Here’s a nice little Bash function in a script to display the elapse time. It’s a nice function for showing how long a process ran.

```
#!/bin/bash
# pass number of seconds as argument. 
# Example below calculates 1000s.
# elapse.sh 1000
function show_time () {
    num=$1
    min=0
    hour=0
    day=0
    if((num>59));then
        ((sec=num%60))
        ((num=num/60))
        if((num>59));then
            ((min=num%60))
            ((num=num/60))
            if((num>23));then
                ((hour=num%24))
                ((day=num/24))
            else
                ((hour=num))
            fi
        else
            ((min=num))
        fi
    else
        ((sec=num))
    fi
    echo "$day"d "$hour"h "$min"m "$sec"s
}
show_time $1
```