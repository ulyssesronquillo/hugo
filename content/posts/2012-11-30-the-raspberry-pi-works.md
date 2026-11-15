---
title: 'the raspberry pi works'
author: ulysses

date: 2012-11-30
slug: the-raspberry-pi-works
draft: false
---

My [Raspberry Pi](http://www.raspberrypi.org) finally arrived yesterday, after what seemed like an eternity of waiting. I ordered it October 24. It was shipped November 20 and arrived on my doorstep November 29. That’s over a month! I had a few hours to play around with it. The first thing I did was placed the Raspberry Pi inside an [Adafruit Rainbow Pibow](http://www.adafruit.com/products/975) enclosure that I’ve ordered several weeks back. It looks amazing. Here’s it is.

![](http://uly.me/wp-content/uploads/2012/11/rpi.jpg)

Once it was inside the Pibow enclosure, I downloaded the Raspberry image called [Raspbian Wheezy](http://www.raspberrypi.org/downloads). I loaded it to an old 4GB SD card that originally came with my Nikon D90 camera. Once the image was loaded, I inserted the SD card, connected a USB keyboard, a USB mouse, and a HDMI cable.

On a side note, I’m currently using a 5v 750ma USB adapter, which I know is sufficient, but the Raspberry Pi needs more ooomp with multiple USB devices connected to it. They recommend that you have at least a 5v 1amp power adapter.

Finally, I powered the Raspberry Pi. A blank screen! Not good. It turned out to be just a resolution issue. I ended up plugging my Raspberry Pi to my old TV, via a RCA composite cable. It worked, although a good portion of the screen was clipped. I started the GUI, then accessed the Terminal and changed the screen resolution from there.

I found this [page](http://raspberrypi.stackexchange.com/questions/1534/how-can-i-change-the-bash-screen-resolution-to-custom-values) with instructions how to change Raspberry Pi to 1680×1050 resolution.

Edit the /boot/config.txt file.

```
sudo nano /boot/config.txt
```

Add the following code to the end of the file. 58 is for screens with a 1680×1050 resolution.

```
hdmi_group=2
hdmi_mode=58
```

Reboot.

```
sudo reboot
```

My monitor works! All 1680×1050 pixels. I ran an update next by issuing the following commands.

```
sudo apt-get update
sudo apt-get upgrade
```

This process takes a good 20 minutes. Finally, I installed Apache.

```
sudo apt-get install apache2
```

Once installed. I checked if the web server works. It does.