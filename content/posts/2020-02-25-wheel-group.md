---
title: 'wheel group'
author: ulysses

date: 2020-02-25
slug: wheel-group
draft: false
---

Here’s an alternate way to give Linux users sudo access by adding them to the wheel group. Most Linux systems come with the wheel group already predefined. By adding users to the wheel group, they now have the ability to sudo and run root commands. The wheel group is in the sudoers file for Redhat, Centos, Debian and Ubuntu.

```
usermod -aG wheel username
```