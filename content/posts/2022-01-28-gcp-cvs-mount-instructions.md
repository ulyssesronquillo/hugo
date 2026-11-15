---
title: 'gcp cvs mount instructions'
author: ulysses

date: 2022-01-28
slug: gcp-cvs-mount-instructions
draft: false
---

Here are the mount instructions for NFS and SMB drives for GCP Netapp CVS.

NFS

```
sudo yum install -y nfs-utils
sudo apt-get install nfs-common
sudo mkdir /condescending-sharp-hugle
sudo mount -t nfs -o rw,hard,rsize=65536,wsize=65536,vers=3,tcp 10.49.253.6:/condescending-sharp-hugle /condescending-sharp-hugle
```

SMB

```
Mapping your network drive
1. Click the Start button and then click on Computer.
2. Click Map Network Drive.
3. In the Drive list, click any available drive letter.
4. In the folder box, type \\shared.mydomain.com\myshare.
To connect every time you log on to your computer, select the Reconnect at sign-in check box.
\\shared.mydomain.com\myshare
5. Click Finish.
```