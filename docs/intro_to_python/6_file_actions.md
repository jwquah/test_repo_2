---
layout: default
title:  File read/write
parent: Introduction to Python
nav_order: 6
---
## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## File Read/Write
+ open arguments:
 + 'w' - write
 + 'r' - read
 + 'a' - append


```python
out = open('C:\\temp\\test.txt', 'w')
out.write('Hello world')
out.write('\n')
out.write('Finish!')
out.close()
```


```python
out = open('C:\\temp\\test.txt', 'a')
out.write('Appending entry')
out.write('\n')
out.write('Finish appending!')
out.close()
```

### Using 'open' to access file


```python
file_handle = open('C:\\temp\\test.txt', 'r')
all_lines = file_handle.readlines()
file_handle.close()

print("All lines: {}".format(all_lines))
### All lines: ['Hello world\n', 'Finish!Appending entry\n', 'Finish appending!']

for line in all_lines:
    line = line.strip()
    print("Each line: {}".format(line))
### Each line: Hello world
### Each line: Finish!Appending entry
### Each line: Finish appending!    
```


### Using 'with' statement to access file


```python
with open('C:\\temp\\test.txt', 'r') as file:
    data = file.read()
    print(data)
### Hello world
### Finish!Appending entry
### Finish appending!    
```


