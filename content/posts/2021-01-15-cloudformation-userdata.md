---
title: 'cloudformation userdata'
author: ulysses

date: 2021-01-15
slug: cloudformation-userdata
draft: false
---

Here’s another way to add startup scripts to your instance during creation.

```
      UserData:
        Fn::Base64: !Sub |
          #cloud-config
          repo_upgrade: none

          runcmd:
            # Cloud init startup script
            - "bash /root/setup.sh"
            
          write_files:
            # Cloud init startup script
            - owner: root:root
              permissions: '0644'
              path: /root/setup.sh
              content: |
                #! /bin/bash -x
          write_files:
            # Cloud init startup script
            - owner: root:root
              permissions: '0644'
              path: /root/setup.sh
              content: |
                #! /bin/bash -x
                # run your bash commands here
                date > log.txt
                uptime >>  log.txt
```

The above script creates a file setup.sh and executes it during instance creation. The output is dumped to log.txt file.