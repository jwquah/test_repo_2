---
layout: default
title:  Flow Control
parent: Introduction to Python
nav_order: 9
---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Flow Control
+ **Break**   : Exits out of the loop if condition is met
+ **Continue**: Returns control to the loop and proceeds to the next if condition is met

### Break
```python
print('Looping from 0 to 10, exiting if value = 5')
var = 0                    
while var < 10:              
   var= var +1
   if var == 5:
      break
   print (var)


### Looping from 0 to 10, exiting if value = 5
### 1
### 2
### 3
### 4

```

### Continue
```python
print('Looping from 0 to 10, skipping if value = 5')
var = 0                    
while var < 10:              
   var= var +1
   if var == 5:
      continue
   print (var)


### Looping from 0 to 10, skipping if value = 5
### 1
### 2
### 3
### 4
### 6
### 7
### 8
### 9
### 10
```