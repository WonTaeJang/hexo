---
title: py-day11-list-5
date: 2021-07-04 14:25:28
   - python 
   - lists
categories: 
   - python
---
# Python - Loop Lists
list items를 사용하여 for loop를 쓸 수 있습니다. 

### example
``` python
thislist = ["apple", "banana", "cherry"]
for x in thislist:
  print(x)
```

## 1. index number를 사용한 loop
range(), len() 함수를 사용하여 for loop 를 응용할 수 있습니다.

### example
``` python
thislist = ["apple", "banana", "cherry"]
for i in range(len(thislist)):
  print(thislist[i])
```

## 2. while loop 
list를 사용하여 while loop도 사용 할 수 있습니다. 
### example
``` python
thislist = ["apple", "banana", "cherry"]
i = 0
while i < len(thislist):
  print(thislist[i])
  i = i + 1
```

# Reference
[w3schools python](https://www.w3schools.com/python)