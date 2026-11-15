---
title: 'encrypt samba share'
author: ulysses

date: 2020-11-16
slug: encrypt-samba-share
draft: false
---

Here’s how to turn on Samba encryption on a share.

Edit /etc/samba/smb.conf on the Samba server.

```
[global]
server max protocol = SMB3
smb encrypt = required 
lanman auth = no
```

Edit /etc/samba/smb.conf on the Samba clients.

```
[global]
smb encrypt = required
client min protocol = SMB2
client max protocol = SMB3
```

To connect.

```
smbclient -e -m SMB3 //xxx.xxx.xxx.xxx/share-name -U username
```