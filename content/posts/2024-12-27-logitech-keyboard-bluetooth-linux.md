---
author: ulysses
title: 'logitech keyboard bluetooth linux'
date: 2024-12-27
slug: logitech-keyboard-bluetooth-linux
draft: false
---

These are the steps taken to make my Logitech K811 keyboard to connect via Bluetooth in Linux Mint.

Run bluetoothctl

```
bluetoothctl
```

In the bluetoothctl command line run these commands. Replace with your own device number.

```
remove 00:XX:XX:XX:XX:1F
scan on
pair 00:XX:XX:XX:XX:1F
connect 00:XX:XX:XX:XX:1F
trust 00:XX:XX:XX:XX:1F
```

You may be asked to type a six digit code to pair the device.
