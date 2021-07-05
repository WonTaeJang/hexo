---
title: py-day12-list-8
date: 2021-07-05 11:10:09
   - python 
   - lists
   - join
categories: 
   - python
---

# Python -Join Lists
## Join Two Lists
몇개의 List를 합치는 방법을 알아보겠습니다.

### example
+ 연산자를 이용한 방법:
``` python
list1 = ["a", "b", "c"]
list2 = [1, 2, 3]

list3 = list1 + list2
print(list3)
```

### example
append() method:
``` python
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

for x in list2:
  list1.append(x)

print(list1)
```

### example
extend() method:
``` python
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

list1.extend(list2)
print(list1)
```

# Reference
[w3schools python](https://www.w3schools.com/python)