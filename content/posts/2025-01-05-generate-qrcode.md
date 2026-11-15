---
author: ulysses
title: 'generate qrcode'
date: 2025-01-05
slug: generate-qrcode
draft: false
---

This is a Python code that generates QR Codes. Save file as qrcode.py. Provide a URL and you're good to go. 

```
import pyqrcode 
from pyqrcode import QRCode 
  
# String which represent the QR code 
s = "https://uly.me"
  
# Generate QR code 
url = pyqrcode.create(s) 
  
# Create and save the png file naming "myqr.png" 
url.svg("site.svg", scale = 8)
```

I use Python's virtual environment for my programs so each one is isolated. Here's the command to start one.

```
python3 -m venv qrcode
```

Activate

```
cd qrcode
source bin/activate
```

You'll need the pyqrcode module before running the program.

```
pip install pyqrcode
```

Finally, run it.

```
python3 qrcode.py
```

Output is site.svg.

![qrcode]({{ site.baseurl }}/wp-content/uploads/2025/01/site.svg)
