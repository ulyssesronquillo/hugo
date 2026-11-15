---
title: 'ssh script'
author: ulysses

date: 2020-10-15
slug: ssh-script
draft: false
---

Here’s my custom ssh script named login.sh using multiple arguments.

```
#!/bin/bash
if [ $# -eq 0 ]
  then
    echo 'no server supplied'
        exit 1
fi
INPUT=$2
case "$INPUT" in
  abc)
    ssh user1@$1
    ;;
  def)
    ssh user2@$1
    ;;
  *)
    ssh user3@$1
    ;;
esac
```

How to use with expected outputs.

```
./login.sh
no server supplied
./login.sh server3 abc
ssh user1@server3
./login.sh server2 def
ssh user2@server2
./login.sh server1
ssh user3@server1
```