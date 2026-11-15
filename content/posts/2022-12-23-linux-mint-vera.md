---
title: 'linux mint vera'
author: ulysses

date: 2022-12-23
slug: linux-mint-vera
draft: false
---

I upgraded to Linux Mint Vera from Una.

```
ulysses@penguin:~/Code$ neofetch
             ...-:::::-...                 ulysses@penguin 
          .-MMMMMMMMMMMMMMM-.              --------------- 
      .-MMMM`..-:::::::-..`MMMM-.          OS: Linux Mint 21.1 x86_64 
    .:MMMM.:MMMMMMMMMMMMMMM:.MMMM:.        Kernel: 5.15.0-56-generic 
   -MMM-M---MMMMMMMMMMMMMMMMMMM.MMM-       Uptime: 13 hours, 35 mins 
 `:MMM:MM`  :MMMM:....::-...-MMMM:MMM:`    Packages: 2176 (dpkg) 
 :MMM:MMM`  :MM:`  ``    ``  `:MMM:MMM:    Shell: bash 5.1.16 
.MMM.MMMM`  :MM.  -MM.  .MM-  `MMMM.MMM.   Resolution: 3840x2160 
:MMM:MMMM`  :MM.  -MM-  .MM:  `MMMM-MMM:   DE: Cinnamon 5.6.5 
:MMM:MMMM`  :MM.  -MM-  .MM:  `MMMM:MMM:   WM: Mutter (Muffin) 
:MMM:MMMM`  :MM.  -MM-  .MM:  `MMMM-MMM:   WM Theme: Mint-Y-Dark-Aqua (Mint-Y) 
.MMM.MMMM`  :MM:--:MM:--:MM:  `MMMM.MMM.   Theme: Mint-Y-Aqua [GTK2/3] 
 :MMM:MMM-  `-MMMMMMMMMMMM-`  -MMM-MMM:    Icons: Mint-Y-Aqua [GTK2/3] 
  :MMM:MMM:`                `:MMM:MMM:     Terminal: gnome-terminal 
   .MMM.MMMM:--------------:MMMM.MMM.      CPU: AMD Ryzen 7 1700X (16) @ 3.700GHz 
     '-MMMM.-MMMMMMMMMMMMMMM-.MMMM-'       GPU: AMD ATI Radeon R7 240/340 / Radeon 520 
       '.-MMMM``--:::::--``MMMM-.'         Memory: 3864MiB / 15928MiB 
            '-MMMMMMMMMMMMM-'
               ``-:::::-``                                         
                                                                   
```

I have 2 issues out of the gate.

1. Audio is crackling.
2. Bluetooth does not automatically connect to my Logitech K11 keyboard.

To fix my audio issues, I have to restart pulseaudio.

```
#!/bin/bash
pulseaudio -k
pulseaudio --start
```

You may have to refresh your browser or restart your app to hear audio.

And here’s the command to connect my keyboard. I’ve provided commands how to scan, connect and pair.

```
#!/bin/bash
# bluetoothctl scan on
# bluetoothctl connect 00:1F:20:A8:EE:1F
# bluetoothctl pair 00:1F:20:A8:EE:1F
# bluetoothctl trust 00:1F:20:A8:EE:1F
# bluetoothctl devices
# bluetoothctl paired-devices
bluetoothctl connect 00:1F:20:A8:EE:1F
```

Output

```
ulysses@penguin:~$ bluetoothctl connect 00:1F:20:A8:EE:1F
Attempting to connect to 00:1F:20:A8:EE:1F
[DEL] Device 72:D9:FF:CC:41:78 72-D9-FF-CC-41-78
[CHG] Device 00:1F:20:A8:EE:1F Connected: yes
[CHG] Device 00:1F:20:A8:EE:1F Modalias: usb:v046DpB317d0900
[CHG] Device 00:1F:20:A8:EE:1F UUIDs: 00001000-0000-1000-8000-00805f9b34fb
[CHG] Device 00:1F:20:A8:EE:1F UUIDs: 00001124-0000-1000-8000-00805f9b34fb
[CHG] Device 00:1F:20:A8:EE:1F UUIDs: 00001200-0000-1000-8000-00805f9b34fb
[CHG] Device 00:1F:20:A8:EE:1F ServicesResolved: yes
[CHG] Device 00:1F:20:A8:EE:1F WakeAllowed: yes
[CHG] Device 00:1F:20:A8:EE:1F Paired: yes
Connection successful
```

The connect command performs both connect and pair.

Hoping they patch this soon so I don’t need to run them @reboot in crontab.