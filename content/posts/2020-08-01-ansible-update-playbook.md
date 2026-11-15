---
title: 'ansible update playbook'
author: ulysses

date: 2020-08-01
slug: ansible-update-playbook
draft: false
---

I have an Ansible playbook that will patch all Ansible clients defined in the Ansible hosts file. The following are contents of my hosts file, and the update playbook.

File: /etc/ansible/hosts

```
[all:vars]
ansible_user='ubuntu'
ansible_become=yes
ansible_become_method=sudo
ansible_python_interpreter='/usr/bin/env python3'
[servers]
server1
server2
server3
[servers:vars]
ansible_python_interpreter=/usr/bin/python3
```

File: /etc/ansible/update.yml

```
---
- hosts: servers
  become: true
  become_user: root
  tasks:
    - name: Update apt repo and cache on all Debian/Ubuntu boxes
      apt: update_cache=yes force_apt_get=yes cache_valid_time=3600

    - name: Upgrade all packages on servers
      apt: upgrade=dist force_apt_get=yes

    - name: Check if a reboot is needed on all servers
      register: reboot_required_file
      stat: path=/var/run/reboot-required get_md5=no

    - name: Reboot the box if kernel updated
      reboot:
        msg: "Reboot initiated by Ansible for kernel updates"
        connect_timeout: 5
        reboot_timeout: 300
        pre_reboot_delay: 0
        post_reboot_delay: 30
        test_command: uptime
      when: reboot_required_file.stat.exist
```

Here’s how I run my Ansible update playbook.

```
ansible-playbook -i /etc/ansible/hosts /etc/ansible/update.yml
```

The advantage of using Ansible is, I can run a single playbook to update dozens of servers. It’s also a great tool for rolling out software as well as executing commands to a group of servers.