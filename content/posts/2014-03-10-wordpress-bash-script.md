---
title: 'wordpress bash script'
author: ulysses

date: 2014-03-10
slug: wordpress-bash-script
draft: false
---

You’ve heard of the famous 5-minute WordPress installation. You might be able to shave off some considerable time if you try installing WordPress from the command line using a Bash script. So, here’s my stab at how to install WordPress from the Linux shell. To be able to do this, you need access to server’s command line or shell as it’s commonly known in the Linux world. Some hosting companies allows you to have access to shell, some don’t. So, your mileage may vary. In this exercise, you need access to it, if you want to perform these functions.

```
#!/bin/bash
sudo wget http://wordpress.org/latest.tar.gz
sudo tar -xzvf latest.tar.gz
sudo mv wordpress/* ./
rm -rf wordpress
rm -f latest.tar.gz
echo "done!"
```

The sequence

The first line tells the system it’s a Bash script.  
The second line downloads the latest WordPress.  
The third line untags or unzips the compressed file.  
The fourth line moves wordpress to the current directory.  
The fifth line deletes the wordpress folder.  
The sixth removes the compressed file.  
The seventh, you echo “done” to the shell.

The fourth line needs a little bit of explaining. By default, when you decompress the WordPress zipped file, it dumps all the files in the “wordpress” directory. It might be your intention to create a sub-folder called “wordpress”, but if that is not what you want to do, then you will need to move all the contents out of the ‘wordpress’ folder and place them in the current directory. That’s what I’m doing here. I’m just moving the WordPress files up one level. After the moving the files, I just delete the now empty ‘wordpress’ folder.

The echo ‘done’ to the screen is just to tell the user that the installation has completed. All you need to do from this point on is to go to your browser and complete the now famous 5-minute installation. Except that you’ll do it at least half the time. Maybe a quarter off the time.