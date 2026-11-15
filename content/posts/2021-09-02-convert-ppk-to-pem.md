---
title: 'convert ppk to pem'
author: ulysses

date: 2021-09-02
slug: convert-ppk-to-pem
draft: false
---

Convert PPK to PEM format.

1. Open Puttygen.
2. Click Load in the Actions section.
3. Select the PPK file you wish to convert.
4. Go to the Conversions menu and select Export OpenSSH key.
5. Click Yes to convert key without a password.
6. Name your private key and save it with a .pem extension.
7. Click Save.

Your pem file should begin with “—–BEGIN RSA PRIVATE KEY—–” and ends with “—–END RSA PRIVATE KEY—–.”

You can also use puttygen in Linux. Install it first.

```
$ sudo apt-get install putty-tools
```

Convert your key.

```
$ puttygen yourkey.ppk -O private-openssh -o yourkey.pem
```

SSH to your server.

```
$ chmod 400 yourkey.pem
$ ssh -i yourkey.pem ec2-user@server-ip
```