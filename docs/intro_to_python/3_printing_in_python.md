---
layout: default
title:  Printing Output
parent: Introduction to Python
nav_order: 3
---

## Printing Methods
+ Note that using ',' to separate will add a space
+ Note the following formats:
 + %d - integer
 + %f - float
 + %s - string


```python
name = 'Ben'
age = 10
print("My name is " + name + ", my age is " + str(age))
### My name is Ben, my age is 10

print("My name is", name, ", my age is ", str(age))
### My name is Ben , my age is  10

print("My name is {}, my age is {}".format(name, age))
### My name is Ben, my age is 10

print("My name is %s, my age is %d" % (name,age))
### My name is Ben, my age is 10
```



## Printing Statements

```python
a,b = 2,3
print (a, b, a+b)
### 2 3 5
print (round (12.34))
### 12
```

```python
a = '''hi, my name is Ben'''
print(a)
###  hi, my name is Ben
```


```python
a = """hi, my name is Ben"""
print(a)
###  hi, my name is Ben
```


```python
a = '''how to spell 'apple' and "banana" in Japanese'''
print(a)
### how to spell 'apple' and "banana" in Japanese
```

```python
# Variable Properties
a = '    28 Jun   2018   '
print("Length: {}".format(len(a)))
### Length: 20

print("Type:   {}".format(type(a)))
### Type:   <class 'str'>
```


```python
# Printing elements in a list
numbers = [1,2,34,7,9,4]
print('Numbers                          : {}'.format(numbers))
### Numbers                          : [1, 2, 34, 7, 9, 4]

factor2 = [x for x in numbers if x % 2 == 0]
print('Values where x mod 2 equal to 0  : {}'.format(factor2))
### Values where x mod 2 equal to 0  : [2, 34, 4]

names = ['BOB','John','peter','JaNE']
print('Names                            : {}'.format(names))
### Names                            : ['BOB', 'John', 'peter', 'JaNE']

names = [x.title() for x in names]
print('Names with first letter uppercase: {}'.format(names))
### Names with first letter uppercase: ['Bob', 'John', 'Peter', 'Jane']

names = [x.lower() for x in names]
print('Lowercase all names              : {}'.format(names))
### Lowercase all names              : ['bob', 'john', 'peter', 'jane']

names = [name for name in names if 'e' in name]
print('Names with "e"                   : {}'.format(names))
### Names with "e"                   : ['peter', 'jane']

```