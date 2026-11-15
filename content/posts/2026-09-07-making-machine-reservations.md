---
author: ulysses
title: 'making machine reservations'
date: 2026-09-07
slug: making-machine-reservations
draft: false
---
An Ansible script that makes multiple machines reservations in a GCP project based on machine type, zone and number of running instances.

The script ... 

- Creates new reservations if it's non-existent with count.
- Update an existing reservation by increasing or decreasing count.
- Delete a reservation if no instances are present or none are running.
- Print a summary at end of the script.

