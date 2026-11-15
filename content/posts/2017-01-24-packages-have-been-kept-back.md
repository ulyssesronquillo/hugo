---
title: 'packages have been kept back'
author: ulysses

date: 2017-01-24
slug: packages-have-been-kept-back
draft: false
---

What do you do when you get this message “the following packages are being kept back.” And what exactly does it mean?

When performing updates in Ubuntu, you typically run these two commands from the command line.

```
$ sudo apt-get update
$ sudo apt-get upgrade
```

If there are updates, it will sometimes ask you to type “Y” or “yes.”

Sometimes you get this message.

```
$ sudo apt-get upgrade                                                                                                
Reading package lists... Done                                                                                                          
Building dependency tree                                                                                                               
Reading state information... Done                                                                                                      
The following packages have been kept back:                                                                                            
  linux-headers-server linux-image-server linux-server                                                                                 
0 upgraded, 0 newly installed, 0 to remove and 3 not upgraded.
```

This means that these packages were not installed or kept back because they have additional packages that are introduced, and the upgrades depend on them.

You can fix this by running:

```
$ sudo apt-get dist-upgrade
```

Or you can individually install the packages you want instead of globally.

```
$ sudo apt-get install package-name
```