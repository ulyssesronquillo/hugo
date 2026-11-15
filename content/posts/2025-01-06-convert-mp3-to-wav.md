---
author: ulysses
title: 'convert mp3 to wav'
date: 2025-01-06
slug: convert-mp3-to-wav
draft: false
---

How to convert a MP3 file to WAV using Python.

```
from pydub import AudioSegment

def convert_mp3_to_wav(mp3_file, wav_file):
    """Converts an MP3 file to WAV format."""

    sound = AudioSegment.from_mp3(mp3_file)
    sound.export(wav_file, format="wav")

if __name__ == "__main__":
    mp3_file = "gettysburg10.mp3"  # Replace with your MP3 file
    wav_file = "output.wav"  # Replace with desired output WAV filename

    convert_mp3_to_wav(mp3_file, wav_file)
    print(f"Conversion complete: {mp3_file} -> {wav_file}")
```


