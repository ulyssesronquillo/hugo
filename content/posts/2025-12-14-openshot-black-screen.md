---
author: ulysses
title: 'openshot black screen'
date: 2025-12-14
slug: openshot-black-screen
draft: false
---
I've been using Openshot video editor to edit or stitch video files.

When exporting to the H.264 format, I've been getting a black screen.

I tried other formats, but it's working only with theora ogg format.

Until I find a fix, I may have to use HandBrake to convert ogg to mp4.

The theora ogg export is super slow. I think I'm have missing codecs.

Update: I was able to fix it. I reinstalled openshot-qt via ppa.

Here are the steps:

1. Uninstall openshot-qt

```
sudo apt purge openshot-qt 
```

2. Install missing codecs

```
sudo apt install libx264-dev libmp3lame-dev
```

3. Install openshot-qt via ppa

```
sudo add-apt-repository ppa:openshot.developers/ppa
sudo apt update
sudo apt install openshot-qt python3-openshot
```

After reinstalling, I'm now able to export to a mp4 format successfully.

No more black screen. However, the exported mp4 file is 1400MB. 

I ran it through HandBrake on Fast 720p30. It's down to 105MB. 

That is all.
