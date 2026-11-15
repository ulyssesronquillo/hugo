---
title: 'how to force downloads'
author: ulysses

date: 2016-07-24
slug: how-to-force-downloads
draft: false
---

Browsers behave differently when it comes to linking media files. Sometimes it will play them directly on the browser. Sometimes it will download them. Each browser seems to have their own rules. So, how do we force all browsers to download media files with just a click of a link.

A simple link like the one below simply won’t work.

```
<a href="video.mp4">Download</a>
```

One way of forcing downloads is to use a [PHP](http://php.net) function called [readfile](http://php.net/manual/en/function.readfile.php).

We have a file below called dl.php. We pass the filename to it, as well as set the path and URL.

```
$filename = $_GET['file'];
$filepath = "http://domain.com/download/";
$url = $filepath.$filename;
header("Content-disposition: attachment; filename=".$filename."");
header("Content-type: application/octet-stream");
readfile("".$url."");
```

Our HTML download link will look like this.

```
<a href="dl.php?file=video.mp4">Download</a>
```

It’s one way of forcing a download via the PHP route.