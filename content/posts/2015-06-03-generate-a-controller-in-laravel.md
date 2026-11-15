---
title: 'generate a controller in laravel'
author: ulysses

date: 2015-06-03
slug: generate-a-controller-in-laravel
draft: false
---

Laravel comes with several generators by way of Artisan CLI or Command Line Interface. To generate a controller, you simply run the following command from the Terminal. This is assuming you’re in the Laravel project folder.

```
// generate a standard Controller
$ php artisan make:controller HomeController

// generate a plain Controller with no methods
$ php artisan make:controller HomeController --plain
```

The first example is the standard way of generating a controller with resourceful routing in mind.

The second example is plain way of generating a controller. It does not contain any method.