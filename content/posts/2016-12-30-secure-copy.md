---
title: 'secure copy'
author: ulysses

date: 2016-12-30
slug: secure-copy
draft: false
---

If you’re logged in to a server via SSH, you can securely copy a file using SCP command tool or also known as “secure copy” to your local desktop, and vice versa. SCP uses SSH for data transfer, authentication and security. Here are several examples on how to use the SCP command line tool if you would like to securely transfer a file to and from your server. You’ll be asked for the user’s password for authentication.

Examples

```
# Copy the file "foobar.txt" from a remote host to the local host
$ scp username@remotehost.com:foobar.txt /your/local/directory
# Copy the file "foobar.txt" from the local host to a remote host
$ scp foobar.txt username@remotehost.com:/some/remote/directory
```

The downside of using SCP is that it is slow. It has been known to be slow. Here’s a quote from [Spikelab’s blog](http://www.spikelab.org/blog/transfer-largedata-scp-tarssh-tarnc-compared.html).

> SCP and the underlying SSH2 protocol implementation in OpenSSH is network performance limited by statically defined internal flow control buffers. These buffers often end up acting as a bottleneck for network throughput of SCP, especially on long and high bandwidth network links.

Despite the poor performance, it’s really not that bad with a tiny bit of patience.

The tradeoff is that you can safely transfer files without sacrificing your security.