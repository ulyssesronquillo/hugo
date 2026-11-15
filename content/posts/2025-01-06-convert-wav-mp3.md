---
author: ulysses
title: 'convert wav mp3'
date: 2025-01-06
slug: convert-wav-mp3
draft: false
---

Here's how to convert a WAV file to MP3 in Python.

```
from pydub import AudioSegment

def convert_wav_to_mp3(wav_file, mp3_file):
    """Converts a WAV file to MP3."""

    sound = AudioSegment.from_wav(wav_file)
    sound.export(mp3_file, format="mp3")

if __name__ == "__main__":
    wav_file = "gettysburg10.wav"
    mp3_file = "output.mp3"
    convert_wav_to_mp3(wav_file, mp3_file)
    print(f"Converted {wav_file} to {mp3_file}")
```

