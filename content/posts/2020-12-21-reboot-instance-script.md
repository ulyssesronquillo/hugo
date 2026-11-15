---
title: 'reboot instance script'
author: ulysses

date: 2020-12-21
slug: reboot-instance-script
draft: false
---

Here’s a new script to reboot a Lightsail instance based on input.

```
#!/bin/bash
echo 'Choose a server to reboot ...'
echo '1) server-one'
echo '2) server-two'
echo '3) server-three'
echo '4) server-four'
echo '5) sever-five'
echo 'q) Quit'
read -p 'Choose a server to reboot: ' server
case $server in 
	1)
		echo 'Rebooting server-one ...'
		aws lightsail reboot-instance --instance-name server-one
		echo 'Done'
		;;
	2)
	        echo 'Rebooting server-two ...'
		aws lightsail reboot-instance --instance-name server-two
		echo 'Done'
		;;
	3)
		echo 'Rebooting server-three ...'
		aws lightsail reboot-instance --instance-name server-three
		echo 'Done'
		;;
	4)
		echo 'Rebooting server-four ...'
		aws lightsail reboot-instance --instance-name server-four
		echo 'Done'
		;;
	5)
		echo 'Rebooting server-five ...'
		aws lightsail reboot-instance --instance-name server-five
		echo 'Done'
		;;
	q)
		echo 'Quit'
		;;
	*)
		echo 'Invalid option' $server
		;;
esac
```

Assuming awscli is working and correct permission is granted to user.