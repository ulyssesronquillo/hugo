---
title: 'use object versioning with cloudfront'
author: ulysses

date: 2020-01-11
slug: use-object-versioning-with-cloudfront
draft: false
---

If you are using AWS CloudFront, you can avoid costly invalidations by using object versioning. Due to the nature of CloudFront, overwriting to the same file will not have any effect until caching is invalidated. The default timeout for CloudFront is 24 hours. If you have a website and you’ve overwritten your logo image, the updated image file will not be reflected on your site due to the caching timeout is 24 hours. To avoid invalidation, enable object versioning by adding a policy when overwriting files.

```
# Logo Image
<a href="logo.png">Website Logo</a>
#
# Implement object versioning. 
# Increase the filename after each logo change.
#
<a href="logo-001.png">Website Logo</a>
<a href="logo-002.png">Website Logo</a>
<a href="logo-003.png">Website Logo</a>
<a href="logo-004.png">Website Logo</a>
```

Each time the logo is updated, change the filename to avoid CloudFront invalidation.