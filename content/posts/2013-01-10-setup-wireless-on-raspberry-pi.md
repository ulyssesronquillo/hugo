---
title: 'setup wireless on raspberry pi'
author: ulysses

date: 2013-01-10
slug: setup-wireless-on-raspberry-pi
draft: false
---

One of the first things you should do once you have your Raspberry Pi is setup a wireless network adapter. This will allow you to be cable free. To configure, you will need one of several approved USB wireless adapters. I’m using an Airlink 101 Wireless N 150 Ultra Mini-USB Adapter that I [purchased](http://www.amazon.com/exec/obidos/ASIN/B006ZZUK5Y/savagehomeaut-20) at Amazon for just $14. I chose the Airline 101 because it was affordable, and it works very well with the Raspberry Pi.

10 steps to setup wireless on Raspberry Pi:

1. Plug in the Airlink 101 adapter.
2. Power up the the Raspberry Pi.
3. To see if the wireless device is recognized, type lsusb.
4. To see if the kernel driver is installed, type lsmod.
5. Edit the /etc/network/interfaces file.
6. Edit the /etc/wpa\_supplicant/wpa\_supplicant.conf file.
7. Reboot.
8. Check with ifconfig.
9. Check with ping.
10. All done.

Here are the commands, instructions and their respected screen outputs.

```
$ lsusb
Bus 001 Device 004: ID 0bda:8176 Realtek Semiconductor Corp. RTL8188CUS 802.11n WLAN Adapter

$ lsmod
8192cu                485042  0

$ sudo nano /etc/network/interfaces
# Add the following lines:
auto wlan0
allow-hotplug wlan0
iface wlan0 inet manual
wpa-roam /etc/wpa_supplicant/wpa_supplicant.conf

$ sudo nano /etc/wpa_supplicant/wpa_supplicant.conf

# Add the following lines:
network={
ssid="The_SSID"
proto=RSN
key_mgmt=WPA-PSK
pairwise=CCMP TKIP
group=CCMP TKIP
psk="The_WPA_SHARED_KEY_"
}

$ sudo reboot

$ sudo ifconfig wlan0

$ ping yahoo.com
```