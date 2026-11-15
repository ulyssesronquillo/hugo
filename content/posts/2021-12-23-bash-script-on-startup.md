---
title: 'bash script on startup'
author: ulysses

date: 2021-12-23
slug: bash-script-on-startup
draft: false
---

How to add bash scripts on startup.

update-rc.d

```
sudo cp /path/to/yourscript.sh /etc/init.d/yourscript.sh
sudo update-rc.d /etc/init.d/yourscript.sh defaults
chmod +x /etc/init.d/yourscript.sh
```

Root Crontab

```
sudo crontab -e
@reboot /path/to/yourscript.sh
```