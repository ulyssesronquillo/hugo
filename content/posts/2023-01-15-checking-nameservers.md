---
title: 'checking nameservers'
author: ulysses

date: 2023-01-15
slug: checking-nameservers
draft: false
---

Handy little script to see if nameserver is on an array.

```
#!/bin/bash
declare -a servers=("127.0.0.53" "127.0.0.52" "127.0.0.51")
client=$(cat /etc/resolv.conf | grep nameserver)
for i in "${servers[@]}"
do
  if [[ $client =~ $i ]]
  then 
    using_unbound="true"
    break
  else
    using_unbound="false"
  fi
done
echo $using_unbound "|" $client
```