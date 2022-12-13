---
layout: default
title:  Function declaration
parent: Introduction to Python
nav_order: 11
---

## Declaring Functions



```python
def get_employee(name):
    num = len(name)
    return name, num

get_employee('Ben')
###  ('Ben', 3)  

get_employee(name='Peter')
### ('Peter', 5) 

(nm,ln) = get_employee('Ben')
print ('My name is: {} and the length is: {}'.format(nm, ln))
### My name is: Ben and the length is: 3
```



When passing arguments to functions, you can pass it as is, or use \*args or \**kwargs. This accepts an arbitrary number of arguments.
+ The single asterisk is used to pass a non-keyworded, variable-length argument list,
+ The double asterisk form is used to pass a keyworded, variable-length argument list

#### Example(s)
```python
def sum (*numbers):
    total_sum = 6
    for num in numbers:
        total_sum += num
    return total_sum

a = sum(1)
print('Return value: {}'.format(a))
### Return value: 7

a = sum(1,2,3,4)
print('Return value: {}'.format(a))
### Return value: 16

num_in = (1,2,3,4,5,6)
b = sum(*num_in)
print('Return value: {}'.format(a))  
### Return value: 27  
```


```python
def display(**names):
    for k, v in names.items():
        print('Name: {}, ID: {}'.format(k,v))

map_dict = {'surendra': 1234, 'ben' : 3456, 'unknwn': 4567}
display(**map_dict)  

### Name: surendra, ID: 1234
### Name: ben, ID: 3456
### Name: unknwn, ID: 4567      
```



```python
def add(x, *rem_ele, **names):
    value = x**2
    total_sum = 6
    for sum in rem_ele:
        total_sum += sum
    for key, value in names.items():
        print('Printing from dictionary: KEY - {}, VALUE - {}'.format(key, value))

    print('Value of {}^2 = {}'.format(x, value))
    print('Total sum = {}'.format( total_sum))

add(4)
### Value of 4^2 = 16
### Total sum = 6

dict_a = { 'a': 'apple'}
add(3, 4, **dict_a)

### Printing from dictionary: KEY - a, VALUE - apple
### Value of 3^2 = apple
### Total sum = 10

numbers = [1,2,3,4]
add(3, 4, *numbers, **dict_a)
### Printing from dictionary: KEY - a, VALUE - apple
### Value of 3^2 = apple
### Total sum = 20
```
