---
title: 'install samba shared drive'
author: ulysses

date: 2013-08-09
slug: install-samba-shared-drive
draft: false
---

What’s not to like with Samba. If you’re not familiar with Samba, it’s an open-source file and printer services which allows disparate clients to share files via SMB/CIFS standard, meaning there’s interoperability between Linux/Unix servers and Windows-based clients. This article will show you how to install a Samba shared drive on an Ubuntu Server.

Install Samba Server

```
sudo apt-get install samba
```

Configure Samba by editing /usr/samba/smb.conf. Uncomment and add the following.

```
security = user

[share]
comment = Ubuntu File Server Share
path = /home/ulysses/share
browsable = yes
guest ok = yes
read only = no
create mask = 0755
```

Create the shared drive.

```
sudo mkdir /home/ulysses/share
sudo chown nobody.nogroup /home/ulysses/share
sudo chmod -R 0777 /home/ulysses/share
```

Restart Samba Server

```
sudo restart smbd
sudo restart nmbd
```

Test the shared drive by accessing it from another computer or from another OS like a Mac or Windows.