---
title: 'detect device, os, browser'
author: ulysses

date: 2014-03-12
slug: detect-device-os-browser
draft: false
---

If you like to deliver specific content to a certain device type, you can use PHP’s server environment settings to know what type of device, operating systems, and browser type is being used. The server environment setting we are interested in is ‘HTTP\_USER\_AGENT.’ This index contains a string that is given off by the user agent, the browser in this case. All devices pass down pieces of information identifying themselves, including the type of device, operating system, and browser that is being used.

If we were to look for an iPad for example, we need to perform the following commands:

```
$iPad   = stripos($_SERVER['HTTP_USER_AGENT'],"iPad");
if ($iPad) { 
  echo 'This is an iPad'; 
} else { 
  echo 'This is not'; 
}
```

Other Devices

```
$user_agent = $_SERVER['HTTP_USER_AGENT'];

$iPad   = stripos($user_agent,"iPad");
$iPod   = stripos($user_agent,"iPod");
$iPhone = stripos($user_agent,"iPhone");
$webOS  = stripos($user_agent,"webOS");
$BlackBerry = stripos($user_agent,"BlackBerry");
$RimTablet= stripos($user_agent,"RIM Tablet");

if (stripos($user_agent,"Android") && stripos($user_agent,"mobile")) { 
  $Android = true;
} elseif(stripos($user_agent,"Android")){
  $AndroidTablet = true;
}

if ($AndroidTablet) {
  echo 'This is an Android Tablet';
} else {
  echo 'This is not an Android Tablet';
}
```

Detect OS Type

```
$user_agent = $_SERVER['HTTP_USER_AGENT'];

if (preg_match('/linux/i', $user_agent)) { $platform = 'linux'; }
if (preg_match('/macintosh|mac os x/i', $user_agent)) { $platform = 'mac'; }
if (preg_match('/windows|win32/i', $user_agent)) { $platform = 'windows'; }

if ($platform == 'windows') {
  // do something
}
```

Detect Browser Type

```
$user_agent = $_SERVER['HTTP_USER_AGENT'];

if (preg_match('/MSIE/i',$user_agent)) { $browser = 'Internet Explorer'; }
if (preg_match('/Firefox/i',$user_agent)) { $browser = 'Mozilla Firefox'; }
if (preg_match('/Chrome/i',$user_agent)) { $browser = 'Google Chrome'; }
if (preg_match('/Safari/i',$user_agent)) { $browser = 'Apple Safari'; }
if (preg_match('/Opera/i',$user_agent)) { $browser = 'Opera'; }
if (preg_match('/Netscape/i',$user_agent)) { $browser = 'Netscape'; }

if ($browser == 'Google Chrome') {
  // do something
} 
```

With the sample code above, you can pretty much single out any device and deliver specific content to it.