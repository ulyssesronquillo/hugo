---
title: 'first page is always selected'
author: ulysses

date: 2013-01-04
slug: first-page-is-always-selected
draft: false
---

I had a little trouble with CodeIgniter pagination today. The pagination function is working fine, but Page 1 is always selected regardless which page I select. The data seems to be correct as I go from one page to another, but the page number doesn’t move at all. Well, after trial and error, the problem turned out to be a configuration issue.

CodeIgniter typically uses the following URI format:

http://domain.com/class/function/id.

The third segment is normally used by the pagination function for navigating from one page to another. By default, CodeIgniter pagination only uses 3 URI segments. If you are using more than 3 segments, then you will need to specify the location of the URI segment in your configuration. In my case, I’m using the fourth segment, I needed to include this setting.

$config \[‘uri\_segment’\] = ‘4’;

If you need help with pagination, please refer to the [Pagination](http://ellislab.com/codeigniter/user-guide/libraries/pagination.html) class from the CodeIgniter [User Guide](http://ellislab.com/codeigniter/user-guide/index.html).