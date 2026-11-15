---
title: 'ubuntu server timezone'
author: ulysses

date: 2017-04-24
slug: ubuntu-server-timezone
draft: false
---

If you want to run a couple of cron jobs, you may need to check if your server is using your timezone. You can determine the server’s timezone by simply typing the system’s date command. You’ll see right away if your server is using the same timezone.

```
$ date
Sun Apr 23 21:21:24 PDT 2017
```

If it isn’t, then you need to change it so it’s in sync with cron jobs. To change timezone, run dpkg-reconfigure tzdata. You’ll be asked to choose a region and the nearest city. In this example, I’m picking the Americas/Los Angeles combination. Choose your own region and city.

```
$ sudo dpkg-reconfigure tzdata
Current default time zone: 'America/Los_Angeles'
Local time is now:      Sun Apr 23 21:24:57 PDT 2017.
Universal Time is now:  Mon Apr 24 04:24:57 UTC 2017.
```

You may need to restart cron so that the new timezone can take effect.

```
$ sudo service cron restart
```