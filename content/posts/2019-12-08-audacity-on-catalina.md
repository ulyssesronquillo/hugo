---
title: 'audacity on catalina'
author: ulysses

date: 2019-12-08
slug: audacity-on-catalina
draft: false
---

If you’ve recently upgraded your Mac to Catalina or Mac OS 10.15.1, you may have noticed that Audacity is no longer working. To get it working, you’ll need to download version Audacity 2.3.3. However, installing and running it normally the way you’ve done it in the past will not be enough. Because of Catalina, Audacity is not able to gain permissions to the microphone inputs. The only way I was able to get it working is to launch Audacity from the Terminal.

Launch Audacity from the Terminal.

```
# cd to Application directory
cd /Applications/Audacity.app/Contents/MacOS
# Run it in the background
bash Audacity.sh &
```

Click Ok if prompted to use the microphone.