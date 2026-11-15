---
title: 'html redirect'
author: ulysses

date: 2015-01-04
slug: html-redirect
draft: false
---

HTML redirect is one of the oldest tricks in the books for web designers. If multiple links share the same information or page for example, you can simply redirect your visitors to a good-known page. Redirect is accomplished using HTML meta redirect. Here’s an example below.

```
<title></title>
<meta content="0; url=http://yahoo.com" http-equiv="refresh"></meta>
```

The url is the website or page you want visitors to be redirected. Content is the number of delay in seconds. The value of 0 means that you want visitors to be redirected immediately. A value of 5 means visitors will be redirected after 5 seconds.