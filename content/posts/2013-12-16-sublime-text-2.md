---
title: 'sublime text 2'
author: ulysses

date: 2013-12-16
slug: sublime-text-2
draft: false
---

[Sublime Text 2](http://www.sublimetext.com/2) is a sophisticated text editor built for writing code, markup and prose. It has a slick user interface with extraordinary features and amazing performance. Sublime Text 2 is available multiple platforms including Windows, Mac OS and Linux OS. After 4 months of heavy use, I now use Sublime Text 2 exclusively. I stopped using other text editors altogether.

Since I work mostly from the Terminal, I wanted to be able to launch Sublime Text 2 directly from the command line. In order to make this possible, I needed to create a symbolic link for easier access. The reason for this is because the Sublime Text 2 command is located in a directory that is hard to remember. So, here’s the command to create a symbolic link called ‘**/bin/subl**‘ for Sublime Text 2.

```
sudo ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" /bin/subl
```

From this point on, every time I needed to edit a file, I simply type the following in the commands from the Terminal:

```
$ subl archives.php
$ subl /etc/hosts
$ subl archives.php footer.php
```

I gave 3 examples above.

In the first example, Sublime Text 2 will launch and open a file from the current directory. The second example will open a file from its full path. The third will open multiple files separated by spaces.