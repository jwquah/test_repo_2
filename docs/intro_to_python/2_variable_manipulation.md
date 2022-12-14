---
layout: default
title:  Variable Manipulation
parent: Introduction to Python
nav_order: 2
---
## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Variable Manipulation


```python
print("'" + a + "' vs '" + a.strip() + "'")
print("'" + a.center(25) + "'")
### '    28 Jun   2018   ' vs '28 Jun   2018'
### '       28 Jun   2018     '
```

### Formatting
```python
a = 'A Cat WalkeD dOwn the street.'
print("Default Output: {}".format(a))
### Default Output: A Cat WalkeD dOwn the street.

print("Upper Output: {}".format(a.upper()))
### Upper Output: A CAT WALKED DOWN THE STREET.

print("Lower Output: {}".format(a.lower()))
### Lower Output: a cat walked down the street.
```

### Replacing a specific word
```python
a = a.replace('Cat', 'Dog')
print (a)
### A Dog WalkeD dOwn the street.
```


### Splitting by delimiter
```python
a = 'apple, boy, cat'
print(a)
### apple, boy, cat
print(a.split(', '))
### ['apple', 'boy', 'cat']
```

### String in string check
```python
'a' in 'apple'
### True
```