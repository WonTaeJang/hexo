---
title: py-day11-list-1
date: 2021-07-04 13:22:02
   - python 
   - lists
categories: 
   - python-list
---

# Python Lists
mylist = ["apple", "banana", "cherry"]

## 1. List
Lists는 단일 변수에 복수개의 itmes를 넣을때 사용합니다.

Lists 말고도 Tuple, Set, Dictionary 가 있고 모두 쓰임새가 다릅니다. 

>- Lists are used to store multiple items in a single variable.
>- Lists are one of 4 built-in data types in Python used to store collections of data, the other 3 are Tuple, Set, and Dictionary, all with different qualities and usage.
>- Lists are created using square brackets:

### example
Create a List:
``` python
thislist = ["apple", "banana", "cherry"]
print(thislist)
```

## 1.1 List Items
List Items은 순서가 지정되고 변경 가능하며 중복 값을 허용합니다.

List Items의 첫번째 index 는 [0] 다음 index는 [1] 순이다.

>List items are indexed, the first item has index [0], the second item has index [1] etc.

## 1.2 Changeable
list가 생성 후 items에 변경, 추가, 제거이 가능합니다. 
>The list is changeable, meaning that we can change, add, and remove items in a list after it has been created.

## 1.3 중복 허용 (Allow Duplicates)
### example
``` python
thislist = ["apple", "banana", "cherry", "apple", "cherry"]
print(thislist)
```

## 1.4 List Length

### example
``` python
thislist = ["apple", "banana", "cherry"]
print(len(thislist))
```

## 1.5 List Items - Data Types
List items는 어떤 data-type도 가능합니다.
### example
``` python
list1 = ["apple", "banana", "cherry"]
list2 = [1, 5, 7, 9, 3]
list3 = [True, False, False]
```

list에는 다른 data-type이 들어가 있어도 됩니다.
### example
``` python
list1 = ["abc", 34, True, 40, "male"]
```

## 1.6 type()
list의 data-type은 'list'입니다.
``` code
<class 'list'>
```

### example
``` python
mylist = ["apple", "banana", "cherry"]
print(type(mylist))
```

## 1.7 list() 생성자
list() 를 사용하여 list 생성자를 생성할 수 있습니다. 
``` python
thislist = list(("apple", "banana", "cherry")) # note the double round-brackets
print(thislist)
```

# Python Collections (Arrays)
Python 프로그래밍 언어에 사용되는 4개의 Collection data types
 - List: 순서가 변경될 수 있으며 중복될 수 있음
 - Tuple: 순서가 지정되고 변경할 수 없음, 중복 허용
 - Set: 순서가 없고 중복이 없음
 - Dictionary: 순서가 지정되고 변경 가능, 중복 없음