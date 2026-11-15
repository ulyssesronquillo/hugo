---
title: 'calculating the ideal efs file size'
author: ulysses

date: 2019-05-09
slug: calculating-the-ideal-efs-file-size
draft: false
---

AWS EFS runs on burst credits when choosing burst mode, which is about 99% of most implementations. The reason for this is that provisioned throughput is very expensive. It’s a $6000 per month commitment. In burst mode, if the EFS volume is too small with heavy IO usage, the burst credits will nose dive. You will eventually run out of burst credits resulting in very poor IO performance. It will be slower than a floppy disk drive. We all know how old that technology is. In order to sustain your burst credits, you’ll need to add data, because more data means you’ll earn burst credits at a higher clip. Here’s how to calculate the ideal file size for an EFS system.

1. Identify your throughput needs by looking at your historical usage. From the Amazon CloudWatch console, check the sum statistic of the TotalIOBytes metric with daily aggregation, for the past 14 days. Identify the day with the largest value for TotalIOBytes.
2. Divide this number by 24 hours, 60 minutes, 60 seconds, and 1024 bytes to get the average KiB/second your application required for that day.
3. Calculate the file system size (in GiB) required to sustain this average throughput by dividing the average throughput number (in KiB/s) by the baseline throughput number (50 KiB/s/GiB) that EFS provides.

For example, let’s say you have a 500 Gib of TotalIOBytes.

500 x 1024 x 1024 x 1024 / (24 x 60 x 60 x 1024) = 6068.15 Kib/s

6068.15 / 50 Kib/s = 121 Gib

You will need about 121 GB of EFS volume size to maintain your burst credits.