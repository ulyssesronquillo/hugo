---
title: 'codeigniter anchor with onclick'
author: ulysses

date: 2013-01-31
slug: codeigniter-anchor-with-onclick
draft: false
---

CodeIgniter comes with a [URL helper](http://ellislab.com/codeigniter/user-guide/helpers/url_helper.html) that assist you with managing URLs. One function worth examining is called anchor, which creates standard HTML links. Instead of the standard HTML &lt;a href=””&gt;anchor&lt;/a&gt; tag most people are familiar with, CodeIgniter coders can take advantage of the simpler anchor function.

To create a standard link, all you have to do is code this:

```
=anchor('blog /index', 'Home');?>

// Output is
<a href="http://yourdomain.com/blog/index.php">Home</a>
```

If you want to add a Javascript popup that will ask you “Are you sure?” before proceeding to the link, then all you have to do is add a third option in the anchor function like this:

```
<?php $onclick = array('onclick'=?>"return confirm('Are you sure?')");?>
=anchor('blog /index', 'Home', $onclick);?>

// Output is
<a href="http://yourdomain.com/blog/index.php" onclick="return confirm('Are you sure?')">Home</a>
```

This function works great especially if you add it to code that delete records. You like to be able to ask the user first if that’s what they really want to do before proceeding.