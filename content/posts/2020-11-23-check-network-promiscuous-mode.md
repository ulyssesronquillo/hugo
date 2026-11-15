---
title: 'check network promiscuous mode'
author: ulysses

date: 2020-11-23
slug: check-network-promiscuous-mode
draft: false
---

Promiscuous mode is a mode for a network interface where the controller to passes all traffic it receives to the CPU instead of passing the frames to the controller. This is helpful if you want to capture all traffic as part of troubleshooting. The question is, how can you tell if your network interface is in a promiscuous mode? Here’s a couple of commands.

Here’s the default mode.

```
sudo ip link show eth0
2: eth0: <broadcast> mtu 1460 qdisc mq state UP mode DEFAULT group default qlen 1000
link/ether xx:xx:xx:xx:xx:xx brd ff:ff:ff:ff:ff:ff
</broadcast>
```

Here’s promiscuous mode. Look for PROMISC.

```
sudo ip link show eth0
2: eth0: <broadcast> mtu 1460 qdisc mq state UP mode DEFAULT group default qlen 1000
link/ether xx:xx:xx:xx:xx:xx brd ff:ff:ff:ff:ff:ff
</broadcast>
```

The other command is netstat. Look for P flag.

```
netstat -i
Kernel Interface table
Iface             MTU    RX-OK RX-ERR RX-DRP RX-OVR    TX-OK TX-ERR TX-DRP TX-OVR Flg
eth0             1460 21895816      0      0 0      22645756      0      0      0 BMPRU
lo              65536    44129      0      0 0         44129      0      0      0 LRU
```

Finally, if you want to enable promiscuous mode, run one of these commands.

```
sudo ip link set eth0 promisc on
ifconfig eth0 promisc
```

To disable, use ifconfig.

```
ifconfig eth0 -promisc
```