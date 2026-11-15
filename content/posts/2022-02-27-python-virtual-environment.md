---
title: 'python virtual environment'
author: ulysses

date: 2022-02-27
slug: python-virtual-environment
draft: false
---

How to create a Python virtual environment.

On Windows

```
$ pip install venv
$ python3 -m venv ~/python-test
```

On Ubuntu

```
$ sudo apt install python3.8-venv
$ python3 -m venv ~/python-test
```

On Mac OS

```
$ brew install virtualenv
$ virtualenv python-test
```

Activate

```
$ cd ~/python-test
$ source bin/activate
```

Deactivate

```
$ deactivate
```