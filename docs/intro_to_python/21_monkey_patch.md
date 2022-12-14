---
layout: default
title:  Monkey Patch
parent: Introduction to Python
nav_order: 21
---

## Monkey patch - mask functions

Monkey patch refers to dynamic (or run-time) modifications of a class or module. This offers programmers a way to do say, critical hotfixes. However, it should be used with caution since this can easily lead to long debug sessions due to behavior disrepancies between code vs runtime.

Below is an example where we overwrite the function definition of randint and 'redirect' it to monkeypatch, which will always return unavailable


```python
import random

random.randint(1, 10)
### 2

def monkey_patch (a, b):
    print('Random function temporarily unavailable')
    print('Sorry for the inconvenience')
    return a,b

random.randint = monkey_patch
random.randint(1, 19)
### Random function temporarily unavailable
### Sorry for the inconvenience
### (1, 19)
```