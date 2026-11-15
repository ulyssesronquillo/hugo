---
title: 'storing git credentials'
author: ulysses

date: 2019-02-09
slug: storing-git-credentials
draft: false
---

There are two ways to store git credentials. One is temporary and the other permanent. You can store your git credentials unencrypted on disk forever or in cache memory temporarily.

Temporary. Store for 15 minutes.

```
git config credential.helper 'cache --timeout=900'
```

Permanent.

```
git config credential.helper store
git push http://example.com/repo.git
Username: <type username="" your="">
Password: <type password="" your="">
</type></type>
```

Next time you use git, you will not be prompted for a password.