---
layout: default
title:  Using OS commands
parent: Introduction to Python
nav_order: 23
---

## Simple OS commands


```python
import os

d = os.system('cd')
d
### 0

d = os.popen('cd').read()
d
### 'C:\\Users\\jwquah\\Downloads\\Python_Training\n'

print(d)
### C:\Users\jwquah\Downloads\Python_Training
```
