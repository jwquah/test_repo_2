---
layout: default
title:  Decorator
parent: Introduction to Python
nav_order: 18
---

### Decorators

Decorators dynamically alter the functionality of a function, method, or class without having to directly use subclasses or change the source code of the function being decorated.

In a sense, allows you to transparently "wrap" the existing function with additional functionality. For example, https://www.oreilly.com/ideas/5-reasons-you-need-to-learn-to-write-python-decorators gives a good example about using decorators to validate (output must be not more than 80 characters long) against different python functions:

```python
def validate_summary(func):
    def wrapper(*args, **kwargs):
        data = func(*args, **kwargs)
        if len(data["summary"]) > 80:
            raise ValueError("Summary too long")
        return data
    return wrapper

@validate_summary
def fetch_customer_data():
    # ...

@validate_summary
def query_orders(criteria):
    # ...

@validate_summary
def create_invoice(params):
    # ...
```    

https://www.thecodeship.com/patterns/guide-to-python-function-decorators/ also offers a good explanation on decorators.

In the example below, the _run_ function is "wrapped" by the *record_output* function so that when any command is issued, the output is written to log.txt


```python
import os
def record_output (func):
    '''
    takes in command and writes result into log file
    '''
    def wrapper(command):
        command = command + " >> log.txt "
        func(command)
    return wrapper


@record_output
def run(command):
    os.system(command)

run('date')

with open('log.txt','r') as fh:
    output = fh.readlines()

print(output)
### ['Fri 07/13/2018 \n']
```
