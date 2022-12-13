---
layout: default
title:  Using OS commands
parent: Introduction to Python
---

## Simple OS commands


```python
import os
d = os.system('cd')
d
```




    0




```python
d = os.popen('cd').read()
d
```




    'C:\\Users\\jwquah\\Downloads\\Python_Training\n'




```python
print(d)
```

    C:\Users\jwquah\Downloads\Python_Training
    
