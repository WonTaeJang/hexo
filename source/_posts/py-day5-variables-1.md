---
title: py-day5-variables-1
date: 2021-07-01 16:46:10
    - python 
    - variables
categories: 
    - python
---
# Python Variables 1
- 변수는 데이터 값을 저장하기위한 컨테이너.
- Variables are containers for storing data values.

## 변수 생성
Python에서는 변수를 선언하는 명령이 없습니다. 
변수는 값을 처음 할당하는 순간 생성됩니다. 

### example
``` python
x = 5
y = "John"
print(x)
print(y)
```

변수는 특정 data type으로 선언 할 필요가 없으며 설정된 후에는 data type을 변경할 수도 있습니다. 

### example
``` python
x = 4       # x is of type int
x = "Sally" # x is now of type str
print(x)
```

## Casting
변수에 data type을 특정하고 싶다면 아래와 같은 Casting 방법이 있습니다.
### example
``` python
x = str(3)    # x will be '3'
y = int(3)    # y will be 3
z = float(3)  # z will be 3.0
```

## Get the Type
변수의 data type을 알고싶다면 type() 함수를 사용하면 됩니다.
### example
``` python
x = 5
y = "John"
print(type(x))  # class <'int'>
print(type(y))  # class <'str'>
```

> data type, casting이 궁금하시면 다음 수업을 기대하세요 (찡긋)

## 작은 따옴표 큰따옴표
문자열 변수는 작은 따옴표 또는 큰 따옴표를 사용하여 선언할 수 있습니다. 
### example
``` python
x = "John"
# is the same as
x = 'John'
```

## 대소문자 구분
변수 이름은 대소 문자를 구분합니다. 
### example
``` python
a = 4
A = "Sally"
#A will not overwrite a
B = "sally"

if A == B:
    print("A and B are equal")
else:
    print("A and B are not equal")
```

# Reference
[w3schools python](https://www.w3schools.com/python/python_syntax.asp)