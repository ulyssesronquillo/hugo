---
title: 'hiding passwords using openssl'
author: ulysses

date: 2023-10-31
slug: hiding-passwords-using-openssl
draft: false
---

How to hide main password on Linux using OpenSSL.

Run this on a web server once.

```
$ echo "SecretPassword" | openssl enc -aes-256-cbc -md sha512 -a -salt -pass pass:NotSoSecretPassword > secret.txt  
$ chmod 600 secret.txt
```

On client machine, download the secret file.

```
$ curl https://webserver/some/dir/secret.txt --output -s secret.txt
```

To retrieve the secret password, run the code below. For added measure, delete secret.txt file afterwards.

```
$ cat secret.txt | openssl enc -aes-256-cbc -md sha512 -a -d -salt -pass pass:NotSoSecretPassword
$rm -f secret.txt
```

In addition, you can rotate the NotSoSecretPassword to make it more secure.