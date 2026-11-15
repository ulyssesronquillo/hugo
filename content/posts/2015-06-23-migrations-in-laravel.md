---
title: 'migrations in laravel'
author: ulysses

date: 2015-06-23
slug: migrations-in-laravel
draft: false
---

Migrations in Laravel is like having version control of your database. It gives you the ability to create, modify and share a schema, as well as drop tables. Since it has version control, you can migrate and rollback your database changes with just a couple of CLI commands. Here’s a couple of examples.

To migrate:

```
$ php artisan migrate
```

To rollback:

```
$ php artisan migrate:rollback
```

In addition, you can also create a new migration table.

```
$ php artisan make:migration create_users_table --create="users"
```

It will create a file similar to this:

app/database/migrations/2015\_01\_01\_213247\_create\_articles\_table.php

which you can modify and add fields.