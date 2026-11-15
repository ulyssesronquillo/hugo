---
title: 'github ssh keys setup'
author: ulysses

date: 2021-11-11
slug: github-ssh-keys-setup
draft: false
---

Here’s how to setup your SSH keys to work with Github.

Generate a key using ed25519 public-key signature system.

```
ssh-keygen -t ed25519
```

It creates a id\_ed25519.pub file.

Go to Github.com and open up Settings &gt; SSH &amp; GPG keys.

Click New SSH key. Give a title and paste your pub key. Authorize.