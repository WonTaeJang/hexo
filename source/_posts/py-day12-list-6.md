---
title: py-day12-list-6
date: 2021-07-05 10:13:29
   - python 
   - lists
   - sort
categories: 
   - python
---

# Python - Sort Lists
List는 sort() method를 이용하여 정렬을 할 수 있다. 
정렬 순으로 영숫자, 오름차순
>List objects have a sort() method that will sort the list alphanumerically, ascending, by default:

### example
``` python
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist.sort()
print(thislist)
```

### example
``` python
thislist = [100, 50, 65, 82, 23]
thislist.sort()
print(thislist)
```

## Sort Descending
내림차순을 사용할려면 reverse = True를 사용하면 된다.
>To sort descending, use the keyword argument reverse = True

### example
``` python
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist.sort(reverse = True)
print(thislist)
```

### example
``` python
thislist = [100, 50, 65, 82, 23]
thislist.sort(reverse = True)
print(thislist)
```

## 대소문자 구별(Case Insensitive Sort)
sort() method는 대소문자를 구별하여 대문자 먼저 정렬이 되고 소문자가 정렬됩니다.
> By default the sort() method is case sensitive, resulting in all capital letters being sorted before lower case letters

### example
``` python
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.sort()
print(thislist)
```

## Reverse Order 
reverse() method를 사용하면 현재 List의 items 순서를 역전 시킨다.
>- What if you want to reverse the order of a list, regardless of the alphabet?
>- The reverse() method reverses the current sorting order of the elements.

### example
``` python
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.reverse()
print(thislist)
```

# Reference
[w3schools python](https://www.w3schools.com/python)