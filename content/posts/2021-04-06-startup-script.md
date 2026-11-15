---
title: 'startup script'
author: ulysses

date: 2021-04-06
slug: startup-script
draft: false
---

Here’s how to run a script on bootup on Rhel 7 that’s running systemd.

First create a script. It this case, it will create a file called test.txt.

```
#!/bin/bash
> /root/test.txt
```

Make the script executable.

```
chmod /root/test.sh
```

Now create a service in /etc/systemd/system/test.service

```
# vi /etc/systemd/system/test.service
[Unit]
Description=A test service
After=network.target
[Service]
Type=simple
ExecStart=/root/test.sh
TimeoutStartSec=0
[Install]
WantedBy=default.target
```

Reload systemd.

```
systemctl daemon-reload
```

Enable the service.

```
systemctl enable test.service
```

Start the service.

```
systemctl start test.service
```

Reboot and test.

```
reboot
```

Validate if the script ran. Check if the file was created.