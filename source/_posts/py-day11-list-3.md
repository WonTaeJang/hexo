---
title: py-day11-list-3
date: 2021-07-04 14:07:52
   - python 
   - lists
categories: 
   - python
---
# python - Change List Items

## 1. item value 변경
### example
``` python
thislist = ["apple", "banana", "cherry"]
thislist[1] = "blackcurrant"
print(thislist)
```

## 2. item value를 range를 통한 변경 (Change a Range of Item Values)

### example
``` python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "mango"]
thislist[1:3] = ["blackcurrant", "watermelon"]
print(thislist)
```

range 범위보다 더 많이 넣거나 적게 넣을 경우 어떻게 되는지 확인해보자.

### example
``` python
thislist = ["apple", "banana", "cherry"]
thislist[1:2] = ["blackcurrant", "watermelon"]
print(thislist)
```

### example
``` python
thislist = ["apple", "banana", "cherry"]
thislist[1:3] = ["watermelon"]
print(thislist)
```

## 3. insert Items
insert() method를 사용하여 해당 index 위치에 value를 넣을수 있다. 

### example
``` python
thislist = ["apple", "banana", "cherry"]
thislist.insert(2, "watermelon")
print(thislist)
```

## 4. add List Items
append() method를 사용하여 list 맨 뒤에 추가할 수 있다. 
### example
``` python
thislist = ["apple", "banana", "cherry"]
thislist.append("orange")
print(thislist)
```

## 5. Extend List
extend() method를 사용하여 list를 붙일 수 있다. 

### example
``` python
thislist = ["apple", "banana", "cherry"]
tropical = ["mango", "pineapple", "papaya"]
thislist.extend(tropical)
print(thislist)
```

## 6. Add Any Iterable
extend() method를 사용하여 collection data type 의 다른 type도 확장이 가능하다.

> The extend() method does not have to append lists, you can add any iterable object (tuples, sets, dictionaries etc.).

### example
``` python
thislist = ["apple", "banana", "cherry"]
thistuple = ("kiwi", "orange")
thislist.extend(thistuple)
print(thislist)
```

# Reference
[w3schools python](https://www.w3schools.com/python)