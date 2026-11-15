---
title: 'aws display lightsail snapshots'
author: ulysses

date: 2021-12-01
slug: aws-display-lightsail-snapshots
draft: false
---

How to display Lightsail snapshots.

```
#!/bin/bash
displaysnapshots () {
  echo '--------------------------------------------------------'
  aws lightsail get-instance-snapshots --query 'instanceSnapshots[].[name]' --output text | sort
  echo '--------------------------------------------------------'
}
displaysnapshots
```

Result.

```
daily_ulyme_1637812801
daily_ulyme_1637899201
daily_ulyme_1637985601
daily_ulyme_1638072001
```

Adding timestamp to the output.

```
aws lightsail get-instance-snapshots --query 'instanceSnapshots[].[name,createdAt]' --output text | sort
```

Result.

```
daily_ulyme_1637812801	1637812806.853
daily_ulyme_1637899201	1637899208.285
daily_ulyme_1637985601	1637985606.184
daily_ulyme_1638072001	1638072006.579
```

Convert Unix timestamp to iso8601. Edit your ~/.aws/config file. Add this line.

```
cli_timestamp_format = iso8601
```

Result.

```
daily_ulyme_1637812801	2021-11-25T04:00:06.853000+00:00
daily_ulyme_1637899201	2021-11-26T04:00:08.285000+00:00
daily_ulyme_1637985601	2021-11-27T04:00:06.184000+00:00
daily_ulyme_1638072001	2021-11-28T04:00:06.579000+00:00
```