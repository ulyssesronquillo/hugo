---
author: ulysses
title: 'display elapse time'
date: 2024-01-03
slug: display-elapse-time
draft: false
---

Here's a simple Bash script that displays how long it takes for a script to run from beginning to end. This is perfect tool for long running scripts that run for hours, and where you need to know much time it took to run from beginning to end. This is ideal for a script that you'll run unattended.

```
#!/bin/bash

log='elapse.log'
>$log

start() {

    start=$(date)
    begin=$(date +%s)
    echo 'Start: '$start | tee -a $log

}

stop() {

    stop=$(date)
    end=$(date +%s)
    echo 'Stop: '$stop | tee -a $log
    elapse=$((end-begin))

}

show_time() {
    num=$elapse
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
    echo "$day"d "$hour"h "$min"m "$sec"s | tee -a $log
}

script() {

    echo "running script now..." | tee -a $log
    sleep 10

}

start
script
stop
show_time
```

In the example above, I'm running a script that echoes text and sleeps for 10s. Here's the output.

```
Start: Wed Jan 3 13:16:44 EST 2024
running script now...
Stop: Wed Jan 3 13:16:54 EST 2024
0d 0h 0m 10s
```

The result says it ran for 10s. You can also view the elapse.log file.

```
$ cat elapse.log
Start: Wed Jan 3 13:16:44 EST 2024
running script now...
Stop: Wed Jan 3 13:16:54 EST 2024
0d 0h 0m 10s
```

