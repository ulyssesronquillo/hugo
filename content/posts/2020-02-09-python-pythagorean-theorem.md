---
title: 'python pythagorean theorem'
author: ulysses

date: 2020-02-09
slug: python-pythagorean-theorem
draft: false
---

Here’s a simple Python program that calculates the hypotenuse of a right angle triangle using the Pythagorean Theory.

a<sup>2</sup> + b<sup>2</sup> = c<sup>2</sup>

```
#!/usr/local/bin/python3
import math
print("================================================")
print("This program will calculate pythagorean theorem.")
print("================================================")
side_A = float(input("Enter side A: "))
side_B = float(input("Enter side B: "))
def pythagoreamTherem(side_A, side_B):
	side_C = math.sqrt(side_A * side_A + side_B * side_B)
	return side_C
side_C = pythagoreamTherem(side_A, side_B)
print("")
print("Side C is: " + "%.2f" % round(side_C,2))
print("")
```

Output

```
ulysses@penguin:~/home/user$ python3 pythagorean.py 
================================================
This program will calculate pythagorean theorem.
================================================
Enter side A: 3
Enter side B: 4

Side C is: 5.00
```