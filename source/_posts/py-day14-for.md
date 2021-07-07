---
title: py-day14-for
date: 2021-07-07 10:36:27
   - python 
   - for
categories: 
   - python
---

# Python For Loops
for loop는 list, tuple, dictionary, set, string등에 순차 반복에 사용된다. 
>A for loop is used for iterating over a sequence (that is either a list, a tuple, a dictionary, a set, or a string).

>This is less like the for keyword in other programming languages, and works more like an iterator method as found in other object-orientated programming languages.

>With the for loop we can execute a set of statements, once for each item in a list, tuple, set etc.

### example
``` python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
  print(x)
```

## 문자열 반복문
### example
``` python
for x in "banana":
  print(x)
```

## break 문
break 문은 loop를 빠져 나올수 있다.
### example
``` python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
  print(x)
  if x == "banana":
    break
```

### example
``` python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
  if x == "banana":
    break
  print(x)
```

## continue 문
continue문은 현재의 반복을 중지하고 다음 반복으로 넘어간다.

### example
``` python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
  if x == "banana":
    continue
  print(x)
```

## range() function
### example
``` python
for x in range(6):
  print(x)
```

``` python
for x in range(2, 6):
  print(x)
```

Increment the sequence with 3 (default is 1):
``` python
for x in range(2, 30, 3):
  print(x)
```

## else in for loop
for문이 끝난뒤 else문을 실행시킬수 있다.
### example
``` python
for x in range(6):
  print(x)
else:
  print("Finally finished!")
```

> note: loop문에 break로 빠져나오게 된다면 else문이 실행되지 않는다.

### example
``` python
for x in range(6):
  if x == 3: break
  print(x)
else:
  print("Finally finished!")
```

## loop 중첩
### example
``` python
adj = ["red", "big", "tasty"]
fruits = ["apple", "banana", "cherry"]

for x in adj:
  for y in fruits:
    print(x, y)
```

## pass 문
for문을 선언하고 사용하지 않을때 pass문을 넣으면 오류가 발생하지 않는다.

### example
``` python
for x in [0, 1, 2]:
  pass
```

[py-exercises-10](https://wontaejang.github.io/2021/07/07/py-exercises-10/)

# Reference
[w3schools python](https://www.w3schools.com/python)