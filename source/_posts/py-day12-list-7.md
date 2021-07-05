---
title: py-day12-list-7
date: 2021-07-05 11:02:24
   - python 
   - lists
   - copy
categories: 
   - python
---

# Python - Copy Lists
python list는 copy() method를 사용하여 list를 복사할 수 있다. 이때 얕은 복사와 깊은 복사를 확실하게 이해하고 넘어가야한다.

## 얕은 복사(shallow copy)와 깊은 복사(deep copy)

### example
얕은 복사:
``` python
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist2 = thislist
thislist.insert(2,"apple")
print(thislist2)
```

### example
깊은 복사:
``` python
thislist = ["apple", "banana", "cherry"]
mylist = thislist.copy()
print(mylist)
```

다른방법으로는 list() 내장 method를 사용

### example
``` python
thislist = ["apple", "banana", "cherry"]
mylist = list(thislist)
print(mylist)
```
# Reference
[w3schools python](https://www.w3schools.com/python)