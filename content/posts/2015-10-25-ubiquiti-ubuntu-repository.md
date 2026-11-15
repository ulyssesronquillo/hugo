---
title: 'ubiquiti ubuntu repository'
author: ulysses

date: 2015-10-25
slug: ubiquiti-ubuntu-repository
draft: false
---

I’m running Ubiquiti’s Unifi Cotroller on one of my websites. I did the sudo apt-get update to perform an update recently and found out that the Ubiquiti’s repository is broken. As it turns out, Ubiquiti has changed the location of their repository to the following location:

```
deb http://www.ubnt.com/downloads/unifi/debian stable ubiquiti
```

You have to edit the /etc/apt/sources.list file to change the previous entry with the one above.

After the change, the update and upgrade went very well.