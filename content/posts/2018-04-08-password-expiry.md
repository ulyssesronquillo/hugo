---
title: 'password expiry'
author: ulysses

date: 2018-04-08
slug: password-expiry
draft: false
---

If you’re asked to change the password expiry or password inactivity for a Linux user, the following command will fix it. It’s ideal in situations where you don’t want the password to expire or you don’t want a user to go inactive. It’s also useful if you want a user to be running automated scripts. Here’s the chage command and its available options.

```
# chage -m 0 -M 99999 -I -1 -E -1 johndoe
```

-m 0 will set the minimum number of days between password change to 0  
-M 99999 will set the maximum number of days between password change to 99999  
-I -1 (number minus one) will set the “Password inactive” to never  
-E -1 (number minus one) will set “Account expires” to never.

To validate a user options, run the following:

```
# chage --list johndoe
Last password change                                    : Apr 4, 2018
Password expires                                        : never
Password inactive                                       : never
Account expires                                         : never
Minimum number of days between password change          : 0
Maximum number of days between password change          : 99999
Number of days of warning before password expires       : 7
```