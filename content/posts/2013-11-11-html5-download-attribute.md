---
title: 'html5 download attribute'
author: ulysses

date: 2013-11-11
slug: html5-download-attribute
draft: false
---

HTML5 has a little-known attribute called download. The download attribute is often used in conjunction with the link or the &lt;a&gt; tag. Check the correct markup for the link tag below. Clicking on a HTML link will typically result in the browser opening up a new page, image, or a document.

In some cases, depending on your browser settings, clicking on a link will download a document, file or an image. For consistency, we can alter the behavior of the link tag by adding the download attribute. Let’s say, we want our readers to download an image, pdf, or a web page. We simply add the download attribute in the link tag.

A typical link looks like this:

```
<a href="page.html">link</a>
```

A link with the download tag would look something like this:

```
<a download="test.jpg" href="random-xxx.jpg">link</a>
```

By adding a filename in the download tag, we are specifying that we want the downloaded file to be renamed to test.png. The download attribute is currently supported on Chrome and Firefox. Safari and IE have not adapted it yet. Click on the Sample link below to see the download tag in action.

[Demo](/demo/bg.jpg)