---
author: ulysses
title: 'logitech keyboard bluetooth issues'
date: 2024-12-17
slug: logitech-keyboard-bluetooth-issues
draft: false
---

I fixed my Bluetooth issues with my Logitech K811 keyboard on Linux Mint

Take note of your device ID in a similar format as a MAC Address.

Here are the steps I took to fix the pairing issue.

Run bluetoothctl, you will get a special prompt.

```
bluetoothctl 
```

Perform a scan. Copy the device ID.

```
scan on
```

Remove the device.

```
remove ID
```

Finally reconnect device.

```
connect ID
trust ID
pair ID
```

You may be prompted to enter the pairing code.

Simply enter the numbers.

That's it.
