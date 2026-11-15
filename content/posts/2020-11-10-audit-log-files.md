---
title: 'audit log files'
author: ulysses

date: 2020-11-10
slug: audit-log-files
draft: false
---

The /var/log/audit/audit.log files were not being rotated. The files in the directory grew so large that it created disk space issues on /. Here’s the fix. In the /etc/audit/auditd.conf file, change max\_log\_file\_action from “ignore” to “rotate.” Instead of hundreds of files being kept, it will be rotated up to 5 files.

```
max_log_file_action = rotate
num_logs = 5
```

 Restart service to take effect. The old files will be deleted.

```
service auditd stop
service auditd start
service auditd status
```

Disk space went from 82% down to 25%.