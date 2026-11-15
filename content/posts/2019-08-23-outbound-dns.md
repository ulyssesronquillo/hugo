---
title: 'outbound dns'
author: ulysses

date: 2019-08-23
slug: outbound-dns
draft: false
---

Here’s a typical setup for an Outbound DNS server.

What are unbound servers? Unbound servers are a validating, recursive and caching DNS server

Install Unbound DNS

```
yum install unbound
```

Configuration: /etc/outbound/outbound.conf

```
server:
        interface: 0.0.0.0
        access-control: 0.0.0.0/0 allow
        local-zone: "10.in-addr.arpa." nodefault
forward-zone:
        name: "10.in-addr.arpa."
        forward-addr: 169.254.169.253
forward-zone:
        name: "ec2.internal"
        forward-addr: 169.254.169.253
forward-zone:
        name: '.'
        forward-addr: 10.10.10.1
        forward-addr: 10.10.11.2
```

Unbound Start, Stop, Restart and Status

```
service outbound start | stop | restart | status
```