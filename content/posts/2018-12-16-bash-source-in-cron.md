---
title: 'bash source in cron'
author: ulysses

date: 2018-12-16
slug: bash-source-in-cron
draft: false
---

I’m running a “source” command inside a Bash script. The script is running fine on its own, but when I try running it inside a crontab, it doesn’t work. I’m using the source command just to load variables in a file, so I don’t have to edit multiple files. As it turns out, the regular shell in crontab does not quite understand the source command, and it’s the very reason the script fails. Here’s an example.

```
source /home/user/server.conf
```

I ended up removing the source line, and hardcoding the variables instead of loading it from a file.

```
server="servername"
```