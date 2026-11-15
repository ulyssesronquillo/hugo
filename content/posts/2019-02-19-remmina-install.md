---
title: 'remmina install'
author: ulysses

date: 2019-02-19
slug: remmina-install
draft: false
---

Remmina is the RDP (remote desktop software) for Windows server on Linux. Here’s how to install.

```
sudo add-apt-repository ppa:remmina-ppa-team/remmina-next
sudo apt-get update
sudo apt-get install remmina remmina-plugin-* libfreerdp-plugins-standard
```

If you don’t see the RDP option, kill the process and restart Remmina.