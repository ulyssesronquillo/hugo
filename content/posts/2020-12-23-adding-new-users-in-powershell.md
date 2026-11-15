---
title: 'adding new users in powershell'
author: ulysses

date: 2020-12-23
slug: adding-new-users-in-powershell
draft: false
---

Here’s an easy way to add Windows users in Powershell.

```
net user username 'password' /add
```

Passwords must meet [requirements](https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements). While you are at it, give it Admin rights.

```
net localgroup Administrators username /add
```