---
title: 'ansible run updates'
author: ulysses

date: 2020-06-18
slug: ansible-run-updates
draft: false
---

Here’s a simple adhoc to run updates on systems in Ansible.

```
ansible servers -m apt -a "upgrade=yes update_cache=yes" -b
```

Results:

```
server | SUCCESS => {
    "changed": false, 
    "msg": "Reading package lists...
     Building dependency tree...
     Reading state information...
     Calculating upgrade...
     0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.", 
    "stderr": "", 
    "stderr_lines": [], 
    "stdout": "Reading package lists...
     Building dependency tree...
     Reading state information...
     Calculating upgrade...
     0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.", 
    "stdout_lines": [
        "Reading package lists...", 
        "Building dependency tree...", 
        "Reading state information...", 
        "Calculating upgrade...", 
        "0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded."
    ]
}
```

If you want to reboot a remote server.

```
ansible servers -m "reboot" -b
```