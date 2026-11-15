---
title: 'counting down the days'
author: ulysses

date: 2015-11-18
slug: counting-down-the-days
draft: false
---

Today, I would like to share with you how to create a WordPress countdown plugin of a future date and time. The plugin output displays the number of days, hours, minutes and seconds left. The plugin uses a WordPress shortcode that you can insert inside your post. A Shortcode makes it easier to display results in WordPress.

Output: \[counting\_down\_the\_days\]

Here’s the plugin code:

```
/*
Plugin Name: Counting Down the Days
Plugin URI: http://uly.me
Description: php countdown
Version: 1.0
Author: Ulysses Ronquillo
Author URI: http://uly.me
*/

// place your php code here

function urr_countdown_days() { 

date_default_timezone_set('Americas/New_York');
$date = strtotime("January 27, 2017 7:15 PM");
$remaining         = $date - time();
$days_remaining    = floor($remaining / 86400);
$hours_remaining   = floor(($remaining % 86400) / 3600);
$minutes_remaining = floor(($remaining-($days_remaining*60*60*24)-($hours_remaining*60*60))/60);
$seconds_remaining = floor(($remaining-($days_remaining*60*60*24)-($hours_remaining*60*60))-($minutes_remaining*60));

return 'There are '.$days_remaining.' days and '.$hours_remaining.' hours and '.$minutes_remaining.' minutes and '.$seconds_remaining.' seconds left.';

}
add_shortcode('counting_down_the_days','urr_countdown_days');
```

The PHP date function is used to calculate the days, hours, minutes and seconds remaining and returns the output. The script is one of many PHP examples online on how to perform countdowns. This was one of the more popular ones. The script also uses the PHP floor function to get the lowest integer while ignoring the leftover fraction or remainder. To use the plugin, place the shortcode ‘counting\_down\_the\_days’ (wrap it in square brackets) anywhere inside your WordPress post.

Output: \[counting\_down\_the\_days\]

If you set a date in the past, the output will say, “Set a future date!”