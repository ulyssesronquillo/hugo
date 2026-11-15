---
author: ulysses
title: 'display ip addresses'
date: 2024-02-04
slug: display-ip-addresses
draft: false
---

Here's a little script to display my internal and external IP addresses.

```
#!/bin/bash

main() {

  my_int_ip=$(ip addr show enp4s0 | grep -w 'inet' | awk '{print $2}')
  my_ext_ip=$(curl -s -4 ifconfig.me)

  echo 'External IP: ' $my_ext_ip 
  echo 'Internal IP: ' $my_int_ip

}

main
```

Output: 

```
External IP: xxx.xxx.xxx.xxx
Internal IP: 192.168.0.100
```

