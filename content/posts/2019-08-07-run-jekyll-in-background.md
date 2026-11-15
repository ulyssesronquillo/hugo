---
title: 'run jekyll in background'
author: ulysses

date: 2019-08-07
slug: run-jekyll-in-background
draft: false
---

Jekyll is a static website generator you can use for developing simple websites. If you are running Jekyll on your desktop, you can view your static website by running a local server. If you want the leave the web server up and running in the background all the time, you can run this command instead.

```
# normally you run this command
jekyll serve
# running it in the background
jekyll serve > /dev/null 2>&1 &
# add incremental which builds only deltas
jekyll serve --incremental > /dev/null 2>&1 &
```

To kill the server, run the following.

```
# find jekyll server process
ps -ef | grep jekyll
# substitute pid# with process id
kill -9 pid#
```