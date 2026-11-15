---
title: 'calculating dates in php'
author: ulysses

date: 2014-02-26
slug: calculating-dates-in-php
draft: false
---

Calculating and formatting dates is an important function when writing software applications. You might be needing to perform a database search of all transactions a month ago, six months ago, etc. To make this all possible, you need to be able to figure out how to calculate dates based from today’s date. PHP has a couple of date functions called date() and mktime(). I use the date() function primarily for formatting dates, and mktime() function for calculating dates since mktime() is the actual Unix timestamp. With these two functions, you can do some pretty amazing date calculations.

Let’s get started.

```
// Today's date
$day   = date("d");
$month = date("m");
$year  = date("Y");

// Using mktime calculate past dates
$start_of_three_months_ago = mktime(0, 0, 0, date("m")-2, 1, date("Y"));
$end_of_three_months_ago   = mktime(23, 59, 59, date("m")-1, 0, date("Y"));

// Using mktime to calculate future dates
$start_of_three_months_from_now = mktime(0, 0, 0, date("m")+3, 1, date("Y"));
$end_of_three_months_from_now   = mktime(23, 59, 59, date("m")+4, 0, date("Y"));

// Formatting dates to 'month day, year' format.
$a = date("M j, Y", $start_of_three_months_ago);
$b = date("M j, Y", $end_of_three_months_ago);
$c = date("M j, Y", $start_of_three_months_from_now);
$d = date("M j, Y", $end_of_three_months_from_now);

// results are based on today's date 
echo $day;
// results in 26
echo $month;
// results in 02
echo $year;
// results in 2014
echo $a;
// results in Dec 1, 2013
echo $b;
// results in Dec 31, 2014
echo $c;
// results in May 1, 2014
echo $d;
// results in May 31, 2014
```

You can then use any set of dates to calculate transactions on the database. For example.

```
SELECT price FROM product WHERE purchase_date BETWEEN $a AND $b;
```

Read more about PHP’s [date](http://www.php.net/manual/en/function.date.php) and [mktime](http://www.php.net/manual/en/function.mktime.php) functions. See [demo](http://uly.me/demo/dates.php). Results are based on today’s date.