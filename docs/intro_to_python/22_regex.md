---
layout: default
title:  Regular Expression
parent: Introduction to Python
nav_order: 22
---

## Regex

Functions:

+ match    - beginning of string
+ search   - everywhere within the string, one time
+ findall  - everywhere within the string, all
+ finditer - everywhere within the string, all iterators


```python
import re

pat = re.compile(r'\d+')

# MATCH
m = pat.match('26 Jan 1999 is my birthday')
m.group()
### '26'

# SEARCH
m = pat.search('26 Jan 1999 is my birthday')
m.group()
### '26'

# FINDALL
m = pat.findall('26 Jan 1999 is my birthday')

for each in m:
    print(each)

### 26
### 1999
```

