---
title: 'simplepie rss reader'
author: ulysses

date: 2014-02-27
slug: simplepie-rss-reader
draft: false
---

If you’re thinking about adding syndication to your website, consider using SimplePie, a super fast and easy-to-use feed parser written in PHP. With SimplePie, adding a RSS feed to your site couldn’t be more easier. In this article, I will show you how to create a RSS page that will display a feed. It will display my blog’s RSS feed as default when nothing is clicked. I’ve included a couple of links that are clickable. When the links are clicked, the RSS feed for that link will be displayed.

First, download [SimplePie](http://simplepie.org/downloads/).

Next, we need to create a file and copy the code below. The code is pretty much self-explanatory.

```
<?php // include SimplePie
require_once('php/autoloader.php');

// Create a new object called $feed
$feed = new SimplePie();

// Set the default to my blog's RSS at first run
if ($_GET[feed] == "") { $_GET[feed]="http://uly.me/feed/"; }
$feed-?>set_feed_url($_GET[feed]);

// Run SimplePie.
$feed->init();

// Send the result to show up on the browser
$feed->handle_content_type();
?>

<a href="rssfeed.php?feed=http://news.yahoo.com/rss">Yahoo News</a> | 
<a href="rssfeed.php?feed=http://feeds.reuters.com/reuters/topNews">Reuter News</a>

<div class="header">
  <h1><a href="<?php echo $feed->get_permalink(); ?>"><?php echo $feed-?>get_title(); ?></a></h1>
  <p><?php echo $feed-?>get_description(); ?></p>
</div>

<?php // Display the feed inside a loop
foreach ($feed-?>get_items() as $item): ?>
<div class="item">
<li><a href="<?php echo $item->get_permalink(); ?>" target="_blank"><?php echo $item-?>get_title(); ?></a></li>
  <p><?php echo $item-?>get_description(); ?></p>
  <p><small>Posted on <?php echo $item-?>get_date('j F Y | g:i a'); ?></small></p>
</div>
<?php endforeach;

/* end of file */
```

See the <a href="http://uly.me/demo/rssfeed.php">demo</a>. Just add your own CSS stylesheet and you're ready to go.