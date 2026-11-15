---
title: 'validating ip addresses'
author: ulysses

date: 2014-01-31
slug: validating-ip-addresses
draft: false
---

If you have a form that accepts IP addresses, you might want to validate it to make sure it really is a valid IP address. I’m talking about IPv4 since IPv6 is not yet universally implemented. A valid IPv4 IP addresses should fall between the numbers 0.0.0.0 and 255.255.255.255. In this example, we will use a regular expression and a pattern matching function in PHP to see if it’s a real IP address.

First things first, we need to sanitize the input. We can use the following PHP functions. We will assign the sanitized input to a variable.

```
// sanitize input from form
$ip_address = addslashes(htmlspecialchars(strip_tags(trim($_POST['ip_address']))));
```

This is the regular expression that we will use that accepts valid IP addresses.

```
// the regular expression for valid ip addresses
$reg_ex = '/^((?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?))*$/';
```

We will now compare the two variables: $reg_ex and $ip_address to see if IP address passes the test.

```
// test input against the regular expression
if (preg_match($reg_ex, $ip_address)) { 
   return TRUE; // it's a valid ip address
}
```

We will now place everything in a tidy function so we can use it anytime we want.

```
function validate_ip_address($ip_address) {
  // sanitized ip address
  $clean_ip_address = addslashes(htmlspecialchars(strip_tags(trim($ip_address))));
  // the regular expression for valid ip addresses
  $reg_ex = '/^((?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?))*$/';
  // test input against the regular expression
  if (preg_match($reg_ex, $clean_ip_address)) { 
    return TRUE; // it's a valid ip address
  }
}
```

Finally, it’s time to call our function.

```
$ip_address = $_POST['ip_address'];
if (validate_ip_address($ip_address)) {
  echo "It's a valid IP address!";
}
```