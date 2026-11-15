---
title: 'cloudfront ssl certificates'
author: ulysses

date: 2019-01-04
slug: cloudfront-ssl-certificates
draft: false
---

If you have SSL on your website, you can import your own SSL certificates into CloudFront, which is a content delivery network service by AWS. You will need to work a few AWS services to get it working.

- CloudFront – create a distribution
- Route 53 – create a hosted zone and add a CNAME
- Certificate Manager – import your SSL certificate

Finally, on the WordPress side, enable the use CloudFront in your SuperCache plugin.

Seems simple, but you’ll need some patience to get it working.

Look at your HTML source to see if your CDN is really working.