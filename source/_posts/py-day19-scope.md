---
title: py-day19-scope
date: 2021-07-19 09:30:48
   - python 
   - scope
categories: 
   - python-scope
---

# Python Scope
변수는 생성된 영역 내에서만 사용할 수 있습니다. 이를 scope 라고 합니다.

## 1. local scope
함수 내에서 변수를 생성하여 사용하면 지역변수이다.

> A variable created inside a function belongs to the local scope of that function, and can only be used inside that function.

### example
``` python
def myfunc():
  x = 300
  print(x)

myfunc()
```

## 1.1 Function Inside Function
함수 내부에 함수에서 지역변수를 접근할 수 있습니다. 

> The local variable can be accessed from a function within the function

### example
``` python
def myfunc():
  x = 300
  def myinnerfunc():
    print(x)
  myinnerfunc()

myfunc()
```

## 2. Global Scope
파이썬 코드의 본문에 생성된 변수는 전역 변수이며 전역 범위에 속합니다.

전역 변수는 전역 및 지역의 모든 범위 내에서 사용할 수 있습니다.

### example
``` python
x = 300

def myfunc():
  print(x)

myfunc()

print(x)
```

## 2.1 Naming Variables
함수 내부와 외부에서 동일한 변수 이름으로 작업하는 경우 Python은 이를 두 개의 개별 변수로 취급합니다. 

하나는 전역 범위(함수 외부)에서 사용 가능하고 다른 하나는 로컬 범위(함수 내부)에서 사용 가능합니다.

### example
``` python
x = 300

def myfunc():
  x = 200
  print(x)

myfunc()

print(x)
```

## 3. Global Keyword
지역 scope에서 global 키워드를 사용하면 전역변수로 사용할 수 있다. 

### example
``` python
def myfunc():
  global x
  x = 300

myfunc()

print(x)
```

# Reference
[w3schools python](https://www.w3schools.com/python)