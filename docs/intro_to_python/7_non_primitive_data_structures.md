---
layout: default
title:  Non-primitive Data Structures
parent: Introduction to Python
nav_order: 7
---

1. TOC
{:toc}

## Non-primitive Data Structures
+ Python supports a mix of non-primitive data structures such as:
 + List
 + Tuple
 + Set
 + Dictionary
 ---

### List
+ A declaration within a square bracket separated by comma
+ Lists are mutable, i.e. you are  able to insert elements into it
+ Useful for manipulating a set of data e.g. adding/removing elements or sorting
+ Index element starts from 0
+ If you convert a string (word) to list, it will split them into single characters


```python
names = ['Ben', 'David', 'Kent', 'mimi']
print('Type: {}'.format(type(names)))
### Type: <class 'list'>

print('Names: {}'.format(names))
### Names: ['Ben', 'David', 'Kent', 'mimi']

print('First Element in names  : {}'.format(names[0]))
### First Element in names  : Ben

print('Second Element in names : {}'.format(names[1]))
### Second Element in names : David
```


```python
fruit = list('apple')
print('Fruit: {}'.format(fruit))
### Fruit: ['a', 'p', 'p', 'l', 'e']
```


### List Manipulation


```python
names = ['mimi',26, 'kent', 25, 'ben', 28, 'mnlee', 29]
print('Names: {}'.format(names))
### Names: ['mimi', 26, 'kent', 25, 'ben', 28, 'mnlee', 29]

print('First Element in names                      : {}'.format( names[0] ))
### First Element in names                      : mimi

print('First to fourth Element in names            : {}'.format( names[0:4] ))
### First to fourth Element in names            : ['mimi', 26, 'kent', 25]
```

 

List format [element_to_start, element_to_end, traversal]. Therefore:

+ [-1:-5:-1]
    * Start from the last index (-1), end at the (-5th) index, step backward every element (-1)
+ [0:8:2]
    * Start from the first index (0), end at the (8th) index, step forward every 2nd element (2)


```python
print('Only the names in the list                  : {}'.format( names[0:8:2] ))
### Only the names in the list                  : ['mimi', 'kent', 'ben', 'mnlee']
print('First to fourth Element in names (reverse)  : {}'.format( names[-1:-5:-1] ))
### First to fourth Element in names (reverse)  : [29, 'mnlee', 28, 'ben']
```



```python
# Append VS Extend
# Append adds an object to the end of a list
# Extend adds an iterable object to the end of a list
fruits = ['apple','banana','apple']
print('Fruits                               : {}'.format(fruits))
### Fruits                               : ['apple', 'banana', 'apple']

fruits.append('durian')
print('Added "durian" to Fruits             : {}'.format(fruits))
### Added "durian" to Fruits             : ['apple', 'banana', 'apple', 'durian']

fruits.extend(['orange','peach'])
print('Added a list(orange, peach) to Fruits: {}'.format(fruits))
### Added a list(orange, peach) to Fruits: ['apple', 'banana', 'apple', 'durian', 'orange', 'peach']
```


```python
fruits = ['apple','banana','cucumber']
print('Fruits                                : {}'.format(fruits))
### Fruits                                : ['apple', 'banana', 'cucumber']

fruits.insert(0,'carrot')
print('Add "carrot" at the front (index [0]) : {}'.format(fruits))
### Add "carrot" at the front (index [0]) : ['carrot', 'apple', 'banana', 'cucumber']

fruits.remove('apple')
print('Remove "apple" from list              : {}'.format(fruits))
### Remove "apple" from list              : ['carrot', 'banana', 'cucumber']

fruits[2] = 'pear'
print('Change "cucumber" to "pear" in list   : {}'.format(fruits))
### Change "cucumber" to "pear" in list   : ['carrot', 'banana', 'pear']

del fruits[1]
print('Delete 2nd entry - banana   from list : {}'.format(fruits))
### Delete 2nd entry - banana   from list : ['carrot', 'pear']

fruits.pop()
print('Remove last entry from list with pop  : {}'.format(fruits))
### Remove last entry from list with pop  : ['carrot']
```



```python
fruits = ['apple','banana','apple']
print('Fruits       : {}'.format(fruits))
### Fruits       : ['apple', 'banana', 'apple']

print('Searching and deleting "apple" from list...')
### Searching and deleting "apple" from list...

num = 0
for fruit in fruits:
    if 'apple' in fruit:
        del fruits[num]
    num +=1

print('Output       : {}'.format(fruits))
### Output       : ['banana']
```



### Nested List


```python
fruits = ['apple', [1,2,3], [4,5,6,7], 'pear', 'carrot']
print('Show 2nd index of list                   : {}'.format(fruits[1]))
### Show 2nd index of list                   : [1, 2, 3]

print('Show 3rd element from 2nd entry of list  : {}'.format(fruits[1][2]))
### Show 3rd element from 2nd entry of list  : 3

print('Show 4th element from 3rd entry of list  : {}'.format(fruits[2][3]))
### Show 4th element from 3rd entry of list  : 7
```


## Tuples
+ A declaration within brackets separated by comma
+ Is just a Collection of items
+ Tuples are immutable, i.e. you are not able to insert elements into a tuple
+ Useful in cases where you need to provide data but do not want it to be changed
+ Index element starts from 0


```python
names = ('ben', 'rais', 'kent', 'mimi', 'mnlee')
print('Type: {}'.format(type(names)))
### Type: <class 'tuple'>

print('Names: {}'.format(names, ))
### Names: ('ben', 'rais', 'kent', 'mimi', 'mnlee')

print('3rd element in tuple: {}'.format(names[2]))
### 3rd element in tuple: kent
```



```python
# You cannot change contents within a tuple!
names[1] = 'boo'
### ---------------------------------------------------------------------------

### TypeError                                 Traceback (most recent call last)

### <ipython-input-94-15c974aea843> in <module>()
###       1 # You cannot change contents within a tuple!
### ----> 2 names[1] = 'boo'


### TypeError: 'tuple' object does not support item assignment
```


## Set
+ A declaration within curly brackets separated by comma
+ Sets are mutable, i.e. you are  able to insert elements into it
+ Holds **unique** values only


```python
a = {1, 2, 3, 4, 5}
b = {2, 4, 6, 8}
c = {3, 6, 9}

print('Set a: {}'.format(a))
### Set a: {1, 2, 3, 4, 5}

print('Set b: {}'.format(b))
### Set b: {8, 2, 4, 6}

print('Set c: {}'.format(c))
### Set c: {9, 3, 6}

print('Elements that exists in a AND b    : {}'.format(a & b))
### Elements that exists in a AND b    : {2, 4}

print('Elements that exists in b AND c    : {}'.format(b & c))
### Elements that exists in b AND c    : {6}

print('Unique elements in a AND b         : {}'.format(a | b))
### Unique elements in a AND b         : {1, 2, 3, 4, 5, 6, 8}

print('Unique elements in b AND c         : {}'.format(b | c))
### Unique elements in b AND c         : {2, 3, 4, 6, 8, 9}

print('Elements that exists in a but NOT b: {}'.format(a - b))
### Elements that exists in a but NOT b: {1, 3, 5}

print('Elements that exists in b but NOT c: {}'.format(b - c))
### Elements that exists in b but NOT c: {8, 2, 4}
```


## Dictionary
+ A key-value pair declaration within curly braces separated by comma
+ Useful in cases where you need to associate values to a specific tag (key)


```python
emp_info = { 1234: 'surendra', 2345: 'some one', 3456: 'cat body'}

print('Dictionary emp_info: {}'.format(emp_info))
### Dictionary emp_info: {1234: 'surendra', 2345: 'some one', 3456: 'cat body'}

print('emp_info of 2345   : {}'.format(emp_info[2345]))
### emp_info of 2345   : some one

print('Keys in emp_info   : {}'.format(emp_info.keys()))
### Keys in emp_info   : dict_keys([1234, 2345, 3456])

print('Values in emp_info : {}'.format(emp_info.values()))
### Values in emp_info : dict_values(['surendra', 'some one', 'cat body'])

print('Items in emp_info  : {}'.format(emp_info.items()))
### Items in emp_info  : dict_items([(1234, 'surendra'), (2345, 'some one'), (3456, 'cat body')])
```



```python
emp_info = { 1234: 'surendra', 2345: 'some one', 3456: 'cat body'}

print('Dictionary emp_info  : {}'.format(emp_info))
### Dictionary emp_info  : {1234: 'surendra', 2345: 'some one', 3456: 'cat body'}

emp_info[8888] = 'new world'
print('Add emp_info 8888    : {}'.format(emp_info))
### Add emp_info 8888    : {1234: 'surendra', 2345: 'some one', 3456: 'cat body', 8888: 'new world'}

del emp_info[8888]
print('Delete emp_info 8888 : {}'.format(emp_info))
### Delete emp_info 8888 : {1234: 'surendra', 2345: 'some one', 3456: 'cat body'}
```




### Summary
+ List supports more operations and therefore consumes more memory space. If your list is large (high number of elements), it will consume a considerable amount of memory
+ Tuple is constant, immutable so uses a set amount of resource
+ For security (constant), consider using tuple, otherwise list is advantageous due to its flexibility
+ Dictionary should be used when you need to store a value matching to a tag (key) such as telephone book. No other data structure enables this.
