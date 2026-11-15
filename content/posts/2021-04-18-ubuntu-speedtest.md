---
title: 'ubuntu speedtest'
author: ulysses

date: 2021-04-18
slug: ubuntu-speedtest
draft: false
---

Install Speedtest CLI.

```
sudo apt-get install gnupg1 apt-transport-https dirmngr
export INSTALL_KEY=379CE192D401AB61
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys $INSTALL_KEY
echo "deb https://ookla.bintray.com/debian generic main" | sudo tee  /etc/apt/sources.list.d/speedtest.list
sudo apt-get update
sudo apt-get install speedtest
```

To run.

```
speedtest
```

Result.

```
$ speedtest
   Speedtest by Ookla
     Server: City of Columbus - Columbus, OH (id = 40410)
        ISP: Spectrum
    Latency:     9.39 ms   (0.63 ms jitter)
   Download:   117.74 Mbps (data used: 60.3 MB)                               
     Upload:    11.81 Mbps (data used: 5.6 MB)                               
Packet Loss:     0.0%
 Result URL: https://www.speedtest.net/result/c/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx (redacted)
```