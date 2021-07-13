---
title: py-day11-list-4
date: 2021-07-04 14:17:37
   - python 
   - lists
categories: 
   - python-list
---

# Python - Remove List Items
remove() method를 사용하여 구체적인 item을 삭제할 수 있다. 

### example
``` python
thislist = ["apple", "banana", "cherry"]
thislist.remove("banana")
print(thislist)
```

## 1. Remove Specified Index
pop() method를 사용하여 구체적인 index의 item을 삭제할 수 있다. 

### example
``` python
thislist = ["apple", "banana", "cherry"]
thislist.pop(1)
print(thislist)
```

### example
구체적인 index를 주지 않으면 마지막 index를 제거한다.
``` python
thislist = ["apple", "banana", "cherry"]
thislist.pop()
print(thislist)
```

### example
del 키워드를 사용하여 해당 인덱스를 삭제할 수도 있다.
``` python
thislist = ["apple", "banana", "cherry"]
del thislist[0]
print(thislist)
```

### example
del 키워드를 사용하여 리스트 모두를 삭제할 수 있다.
``` python
thislist = ["apple", "banana", "cherry"]
del thislist
```

## 2. Clear the List
clear() method 를 사용하여 list 내부에 item을 모두 제거한다(list는 남아있음).

### example
``` python
thislist = ["apple", "banana", "cherry"]
thislist.clear()
print(thislist)
```

# Reference
[w3schools python](https://www.w3schools.com/python)