---
author: ulysses
title: 'linux mint dummy output'
date: 2024-05-26
slug: linux-mint-dummy-output
draft: false
---
Somehow I lost my audio devices in Linux Mint. Instead, the only audio device present in the system is the 'dummy output.' Googling for answers was not clear cut. After many trials and errors I was able to get my sound fixed. Here are the commands I took to get my audio devices back in the fold in Linux Mint. Your mileage may vary.

First, validate your sound devices are still present or being recognized on your system.

```
aplay -l
```

You can try also Alsa. You may have to install it first.

```
sudo apt install alsa-utils 
alsamixer -c 1
```

Then remove and purge pulseaudio and start fresh.

```
rm -r ~/.config/pulse/
pulseaudio -k
killall pulseaudio
apt remove pulseaudio
apt purge pulseaudio 
reboot
```

After reboot, reinstall pulseaudio.

```
apt install pulseaudio
```

Make sure to enable and to start pulseaudio on bootup.

```
systemctl --user enable pulseaudio
systemctl --user start pulseaudio
systemctl --user status pulseaudio
```

Your sound devices should load. You should be able to hear again.