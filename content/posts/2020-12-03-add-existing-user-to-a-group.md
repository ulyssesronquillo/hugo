---
title: 'add existing user to a group'
author: ulysses

date: 2020-12-03
slug: add-existing-user-to-a-group
draft: false
---

Here’s how to add an existing user to a user group in Linux.

```
usermod -a -G groupname username
usermod -a -G www-data john
```

List all users belonging to a group.

```
lid -g www-data
```

List all the groups the user belongs to.

```
groups john
```