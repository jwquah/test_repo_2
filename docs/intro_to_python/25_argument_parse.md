---
layout: default
title:  Parsing Arguments
parent: Introduction to Python
nav_order: 25
---

## Parsing Arguments

Save the below into a script e.g. `script.py`
```python
import sys

name = svs.argv[0]
age = sys.argv[1]
print("your name is" , name)
print("your age is" , age)
```

When executed:

	% script.py casper 10
	>>> your name is casper
	>>> your age is 10

