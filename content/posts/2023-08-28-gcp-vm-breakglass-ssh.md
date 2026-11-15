---
title: 'gcp vm breakglass ssh'
author: ulysses

date: 2023-08-28
slug: gcp-vm-breakglass-ssh
draft: false
---

When you exhausted all efforts trying to login to a VM and there’s no other way to log in to the server, here’s a breakglass method to allow you to log in to a VM via a startup script. Just add the following bash script to the VM startup section. Change the username and password to your liking. Restart the server to trigger the startup script. After reboot, it should give you access to the server. In addition, you will also have sudo access so you can switch as root.

1\. Edit the VM.  
2\. Go to the Startup script section and add the following.

```
#!/bin/bash
user="johndoe"
pass="password"
if id $user >/dev/null 2>&1; then
    exit
else
    adduser 
    echo $user:$pass | chpasswd
    usermod -aG google-sudoers $user
fi
```

3\. Restart the server.  
4\. Log in as user.  
5\. Fix the login issue.  
6\. Remove user.  
7\. Remove the startup script.