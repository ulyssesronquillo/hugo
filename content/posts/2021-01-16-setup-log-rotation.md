---
title: 'setup log rotation'
author: ulysses

date: 2021-01-16
slug: setup-log-rotation
draft: false
---

Logrotation is available in most Linux distros. If they are missing, you can easily install them. The logrotation main configuration file is located in /etc/logrotate.conf which is the default setting. The config file contains an include statement that pulls in other log configurations located in the /etc/logrotate.d/ directory. When setting up a log rotation, it’s best to add your log rotation configuration in this directory.

Here’s a simple configuration in a file called webmon.

```
/home/ubuntu/webmon.log {
        daily
        create 0640 ubuntu ubuntu
        dateext
        rotate 7
	nocompress
}
```

The options above does the following:

- The logs are rotated daily.
- The logs are rotated 7 times with no compression.
- The rotate log files will have dates appended to them.
- The log files are owned user ubuntu with permission of 0640.

There are more options from the [logrotate](https://linux.die.net/man/8/logrotate) man pages which can be added.