---
title: 'run code at specific times'
author: ulysses

date: 2015-01-20
slug: run-code-at-specific-times
draft: false
---

If you need to run some code at certain times of the week, a weekly sale for example, PHP gives you that flexibility. In the example below, we will display an image on our website every Wednesday afternoon between 1pm and 5pm to display a sale.

Let’s create a new function called wednesday\_afternoon(). We can use this function to check the date and time. The function checks for the current time and compares it if it’s Wednesday afternoon. It returns a true if it is, and a false if it falls outside those times.

```
function wednesday_afternoon() {
  date_default_timezone_set('America/Los_Angeles');
  $start_time = strtotime('Wednesday 1pm');
  $stop_time = strtotime('Wednesday 5pm');
  $current_time = strtotime('now');
  // return true if between start and stop times
  if ( $current_time > $start_time && $current_time 
```

A simple if statement decides what image to display based if it's Wednesday afternoon.

```
if (wednesday_afternoon()) {
  <div class="wednesday_sale">
    <img decoding="async" src="/path/to/our/image.png"></img>
  </div>
} else {
  <div class="no_sale">
    <img decoding="async" src="/path/to/our/no/sale/image.png"></img>
  </div>
}
```

I have posted a <a href="https://gist.github.com/ulyssesr/520100748a5ef573f865">similar code</a> GitHubGist.