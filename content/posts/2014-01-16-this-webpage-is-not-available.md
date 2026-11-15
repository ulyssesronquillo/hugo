---
title: 'this webpage is not available'
author: ulysses

date: 2014-01-16
slug: this-webpage-is-not-available
draft: false
---

I stopped by Starbucks to hang out, sip coffee, and perform some housecleaning on my website. I fired up my MacBook Air and tried to access my website. Chrome barked at me saying, “This webpage is not available.” What! So, I opened up Terminal to see if I’m really connected to the WiFi network. Yes, I am. I can ping everything else, but my domain.

So, what’s happening? Is my site down? I logged into my VPS. The server is doing just fine. I did some more investigating. I realized that I can ping my IP address, but not the domain. That’s interesting. AT&T is currently the provider for the WiFI for Starbucks.

A few weeks ago, I saw a blurb on the news that Google will provide WiFi for Starbucks. As far as I know, that hasn’t happened yet, at least not at this Starbucks location. Google plans to roll out its WiFi services to Starbucks in the next few months. So, we are still months away from that coming into fruition.

Is AT&T blocking my domain? I have AT&T DSL at home. I can access my domain just fine. So, whoever is managing the AT&T WiFi, must be applying some kind of filtering to block certain domains from working.

Since I can still ping my IP Address, I decided to just edit my hosts file.

For Macs, the hosts file is located in /private/etc/hosts.

```
$ sudo nano /private/etc/hosts
```

I added a host a new entry to resolve my domain to my server’s IP address.

```
127.0.0.1       localhost
255.255.255.255 broadcasthost
::1             localhost
173.255.251.194 uly.me
```

I saved the new entry, and pinged my domain! It works! I opened up the browser to access my website. It works!

I’m glad I was able to find a workaround! However, I’m still perplexed as to why my domain is being blocked.
