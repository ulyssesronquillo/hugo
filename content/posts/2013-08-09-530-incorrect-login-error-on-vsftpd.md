---
title: '530 incorrect login error on vsftpd'
author: ulysses

date: 2013-08-09
slug: 530-incorrect-login-error-on-vsftpd
draft: false
---

I installed a FTP server called vsftpd on my Ubuntu Server recently. After the install, I’ve been unable to login at all. It turned out to be a bug within the vsftpd program. I found a fix [here](http://www.jackenhack.com/vsftpd-ubuntu-server-530-login-incorrect-error-fixed/). Essentially, the fix was removing the vsftpd program first, deleting the /etc/pam.d/vsftpd file and forcing the application to recreate the file. The third step is to reinstall the vstfpd once again.

From the Terminal, type the following commands.

```
sudo apt-get remove vsftpd
sudo rm /etc/pam.d/vsftpd
sudo apt-get install vsftpd
```

After making the changes, I was able to log in successfully using the Filezilla client. Success.