---
title: 'ansible run commands'
author: ulysses

date: 2020-08-02
slug: ansible-run-commands
draft: false
---

Typically you will run Ansible using playbooks, just like the playbook that I ran from the previous post to patch a bunch of servers all at once. In addition to running playbooks, you can also run single ad hoc commands to a server or to a group of servers. Below are a few examples of that.

First, here’s my /etc/ansible/hosts file.

```
[servers]
server1
server2
[webservers]
server3
server4
[appservers]
server5
server6
[dbservers]
server7
server8
```

Here are the commands.

```
ansible servers -m ping
ansible webservers -m command -a "df -h"
ansible appservers -m command -a "crontab -l"
ansible dbservers -m command -a "cat /etc/hosts"
ansible all -m command -a "cat /etc/passwd"
ansible webservers -m command -a "systemctl status apache2"
ansible appservers -m command -a 'uptime'
```

The first command runs ping on server1 and server2. The second command displays disk information of server3 and server4. The third command displays the crontab of server5 and server6, and so on and on. You get the drift.