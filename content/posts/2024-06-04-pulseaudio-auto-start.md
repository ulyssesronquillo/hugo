---
author: ulysses
title: 'pulseaudio auto start'
date: 2024-06-04
slug: pulseaudio-auto-start
draft: false
---
I'm trying to figure out why my audio is not automatically starting on Linux.

After some trial and error, here's the fix.

Edit the /etc/pulse/client.conf file. 

```
vi /etc/pulse/client.conf
```

Change "autospawn=no" to "autospawn=yes."

```
autospawn=yes
```

Make sure to take out ';' or '#" to remove the comment.

```
pulseaudio --start 
```

Once you modified the file, restart pulseaudio.

```
pulseaudio --start
```

Reboot your machine to check if audio is working on boot.

If that doesn't work, delete the cookie.

```
rm -f ~/.config/pulse/cookie
```

You can restart the service.

```
systemctl --user restart pulseaudio
```

In addition, running this command worked if audio does not load automatically.

```
pulseaudio -k
```

In my case, I added the following to my Startup Applications because it wasn't loading properly.

```
systemctl --user restart pulseaudio
```

Enjoy.
