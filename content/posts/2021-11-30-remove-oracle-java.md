---
title: 'remove oracle java'
author: ulysses

date: 2021-11-30
slug: remove-oracle-java
draft: false
---

Here’s a script that removes Oracle Java on your system. Installs OpenJDK Hotspot as a replacement.

```
#!/bin/bash
# set env
oracle_jre_version="jdk1.8.0_172"
open_jre_version="java-1.8.0-openjdk"
# REMOVE LINKS
deljdk () {
	sudo update-alternatives --remove "java" "/usr/lib/jvm/$oracle_jre_version/bin/java"
	sudo update-alternatives --remove "javac" "/usr/lib/jvm/$oracle_jre_version/bin/javac"
	sudo update-alternatives --remove "javaws" "/usr/lib/jvm/$oracle_jre_version/bin/javaws"
}
# REMOVE RPM
delrpm () {
	jdk=$(rpm -qa | grep jdk-1.7)
	rpm -e $jdk
	jdk=$(rpm -qa | grep jdk1.8)
	rpm -e $jdk
	sudo rm -rf /usr/java/jdk*
}
# REMOVE SYMBOLIC LINKS
delsym () {
	rm /usr/java/default /usr/java/latest
	rm /usr/lib/mozilla/plugins/libnpjp2.so
	rm /usr/lib/mozilla/plugins/libnpjp2.so
}
# INSTALL OPENJDK
addjdk () {
	cd /usr/java
	rm -f /usr/java/OpenJDK8U-jdk_x64_linux_hotspot_8u302b08.tar.gz
	wget --no-check-certificate https://10.49.39.125/download/OpenJDK8U-jdk_x64_linux_hotspot_8u302b08.tar.gz
	tar xzf OpenJDK8U-jdk_x64_linux_hotspot_8u302b08.tar.gz
	chown -R username:username /usr/java/jdk8u302-b08
}
# ADD PATH
addpath () {
	sed -i '/jdk8u302-b08/d' /home/username/.zshrc
	sed -i '/jdk8u302-b08/d' /home/username/.profile
	echo 'export PATH=/usr/java/jdk8u302-b08/bin:$PATH' | tee -a ~/.bashrc
	echo 'export PATH=/usr/java/jdk8u302-b08/bin:$PATH' | tee -a /home/username/.zshrc
	echo 'export PATH=/usr/java/jdk8u302-b08/bin:$PATH' | tee -a /home/username/.profile
	chown username:username /home/username/.zshrc
	chown username:username /home/username/.profile
}
deljdk
delrpm
delsym
addjdk
addpath
```