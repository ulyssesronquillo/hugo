---
title: 'set timezone permanently'
author: ulysses
classic-editor-remember:
    - classic-editor
date: 2021-03-18
slug: set-timezone-permanently
draft: false
---

It’s recommended to set the clock to UTC. In rare occasions, local time may be needed.

Here’s how to set your server’s timezone permanently.

Check the date first.

```
date
```

Backup localtime. Set it to US Eastern Time.

```
mv /etc/localtime /etc/localtime.backup
ln -s /usr/share/zoneinfo/America/New_York /etc/localtime
```

Backup clock. Set it to US Eastern Time.

```
cp -p /etc/sysconfig/clock /etc/sysconfig/clock.backup 
> /etc/sysconfig/clock
echo ZONE=\"America/New_York\" > /etc/sysconfig/clock
```

Run the date again to validate.

```
date
```