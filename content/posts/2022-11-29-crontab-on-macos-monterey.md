---
title: 'crontab on macos monterey'
author: ulysses

date: 2022-11-29
slug: crontab-on-macos-monterey
draft: false
---

A recent OS upgrade rendered the crontab to malfunction on macOS Monterey. It turned out the system just needed a reset of System Preferences &gt; Security &amp; Privacy &gt; Privacy tab, and to make sure cron has full access to disks. Once you flipped that, your crontab should start working. Hope that helps.