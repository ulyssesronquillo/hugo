---
title: 'restart rpc gssd service'
author: ulysses

date: 2021-01-31
slug: restart-rpc-gssd-service
draft: false
---

If a Linux user is having an access problem with a NFS share, and particularly with key expiration, then check if the RPC GSSD service is up and running. NFS clients uses the RPCSEC\_GSS protocol to establish security credentials with a NFS server using Kerberos authentication.

Here’s an example of a key expire error due to a NFS client not authenticated properly.

```
df -h
df: '/data/dir1': Key has expired
df: '/data/dir2': Key has expired
df: '/data/dir3': Key has expired
```

Check if RPC GSSD service is healthy. Restart the service if there are credential errors.

```
service rpc-gssd status
```

Here’s one with an authentication issue.

```
[root@server ~]# service rpc-gssd status
Redirecting to /bin/systemctl status rpc-gssd.service
● rpc-gssd.service - RPC security service for NFS client and server
   Loaded: loaded (/usr/lib/systemd/system/rpc-gssd.service; static; vendor preset: disabled)
   Active: active (running) since Sun 2021-01-31 03:16:43 CST; 2h 14min ago
 Main PID: 710 (rpc.gssd)
   Memory: 1.6M
   CGroup: /system.slice/rpc-gssd.service
           └─710 /usr/sbin/rpc.gssd
 
Jan 31 03:17:10 server.domain.com rpc.gssd[710]: ERROR: gssd_refresh_krb5_machine_credential: no usable keytab entry found
Jan 31 03:17:10 server.domain.com rpc.gssd[710]: ERROR: No credentials found for connection to server nas.domain.com
Jan 31 03:17:10 server.domain.com rpc.gssd[710]: ERROR: gssd_refresh_krb5_machine_credential: no usable keytab entry found
Jan 31 03:17:10 server.domain.com rpc.gssd[710]: ERROR: No credentials found for connection to server nas.domain.com
```

Restart the service.

```
service rpc-gssd stop
service rpc-gssd start
```

 Here’s a service that’s healthy.

```
[root@server ~]# service rpc-gssd status
Redirecting to /bin/systemctl status rpc-gssd.service
● rpc-gssd.service - RPC security service for NFS client and server
   Loaded: loaded (/usr/lib/systemd/system/rpc-gssd.service; static; vendor preset: disabled)
   Active: active (running) since Sun 2021-01-31 05:33:54 CST; 28min ago
  Process: 9809 ExecStart=/usr/sbin/rpc.gssd $GSSDARGS (code=exited, status=0/SUCCESS)
 Main PID: 9810 (rpc.gssd)
   Memory: 804.0K
   CGroup: /system.slice/rpc-gssd.service
           └─9810 /usr/sbin/rpc.gssd

Jan 31 05:33:54 server.domain.com systemd[1]: Starting RPC security service for NFS client and server...
Jan 31 05:33:54 server.domain.com systemd[1]: Started RPC security service for NFS client and server.
```