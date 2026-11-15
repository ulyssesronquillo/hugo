---
title: 'github generate a key'
author: ulysses

date: 2021-12-10
slug: github-generate-a-key
draft: false
---

Generate a ssh key for Github

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Copy and paste the ‘id\_ed25519.pub’ key to Github.

```
cd .ssh
$ ls -l 
-rw-r--r-- 1 ulysses ulysses   537 Jul 14 12:54 id_ed25519
-rw-r--r-- 1 ulysses ulysses   194 Jul 14 12:54 id_ed25519.pub
```

Go to Settings &gt; SSH and GPG keys. Add new SSH key and authorize.

You can then clone using the SSH format.

```
$ git init
$ git clone git@github.com:acoount/repo.git
```