---
title: py-day11-booleans
date: 2021-07-04 12:13:00
    - python 
    - bool
categories: 
    - python-booleans
---

# Python Booleans
Booleans는 True, False 둘중 하나의 값을 나타냅니다.

## 1. Boolean Values
두 값을 비교할때 값이 평가 되고 Boolean을 반환 한다.

### example
``` python
print(10 > 9)   # True
print(10 == 9)  # False
print(10 < 9)   # False
```

if 문에서 조건을 실행하면 Python은 True또는 False다음을 반환합니다.

### example
조건 이 True 또는 False 인지에 따라 메시지가 다르게 출력됩니다.
``` python
a = 200
b = 33

if b > a:
  print("b is greater than a")
else:
  print("b is not greater than a")
```

## 2. 값, 변수 평가
### example
문자열과 숫자를 평가합니다.
``` python
print(bool("Hello"))
print(bool(15))
```

### example
변수를 평가합니다. 
``` python
x = "Hello"
y = 15

print(bool(x))
print(bool(y))
```

## 3. 대부분의 값은 True
- 빈 문자열을 제외하고 string은 True
- 숫자 0을 제외하고 True
- 비어있는 것을 제외한 list, tuple, set, dictionary는 True

### example
``` python
bool("abc")
bool(123)
bool(["apple", "cherry", "banana"])
```

## 4. False인 값
### example
``` python
bool(False)
bool(None)
bool(0)
bool("")
bool(())
bool([])
bool({})
```

## 5. 함수는 Boolean을 반환할수 있다. (Functions can Return a Boolean)
### example
``` python
def myFunction() :
  return True

print(myFunction())
```

함수의 부울 응답을 기반으로 코드를 실행할 수 있습니다.
### example
``` python
def myFunction() :
  return True

if myFunction():
  print("YES!")
else:
  print("NO!")
```

>Python also has many built-in functions that return a boolean value, like the isinstance() function, which can be used to determine if an object is of a certain data type:

### example
``` python
x = 200
print(isinstance(x, int))
```

# Exercises
[py-exercises-5](https://wontaejang.github.io/2021/07/04/py-exercises-5/)

# Reference
[w3schools python](https://www.w3schools.com/python)