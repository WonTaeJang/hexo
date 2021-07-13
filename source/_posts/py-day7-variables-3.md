---
title: py-day7-variables-3
date: 2021-07-02 10:12:20
    - python 
    - variables
    - Global
categories: 
    - python-variables
---

# Python Variables 3
변수(Varialble)	값이 저장된 메모리 공간의 주소를 가르키는 식별자(identifier)

## 1. 전역 변수(Global Variables)
이때까지 보았던 예제들과 같이 함수 외부에서 생성 된 변수를 전역 변수라고 합니다. 

**전역 변수는 함수 내부와 외부 모두에서 사용할 수 있습니다.**

### example
함수 외부에서 변수를 만들고 함수 내부에서 사용
``` python
x = "awesome"

def myfunc():
  print("Python is " + x)

myfunc()
```

- 함수 내에서 동일한 이름으로 변수를 생성하면 변수는 지역 변수가되며 함수 내에서만 사용할 수 있습니다.

- 동일한 이름의 전역 변수는 원래 값으로 전역 및 원래 상태로 유지됩니다.

### example
전역 변수와 이름이 같은 함수 내부에 변수를 만듭니다.
``` python
x = "awesome"

def myfunc():
  x = "fantastic"
  print("Python is " + x)

myfunc()

print("Python is " + x)
```

## 2. global 키워드
일반적으로 함수 내부에 변수를 만들면 해당 변수는 로컬(지역)이며 해당 함수 내에서만 사용할 수 있습니다.

함수 내에 전역 변수를 만들려면 global키워드를 사용할 수 있습니다 .

### example
global키워드 를 사용하는 경우 변수는 전역 범위에 속합니다.
``` python
def myfunc():
  global x
  x = "fantastic"

myfunc()

print("Python is " + x)
```

함수 내에서 전역 변수를 변경 하려면 global키워드를 사용하면 됩니다.

### example
함수 내 전역 변수의 값을 변경하려면 global키워드 를 사용하여 변수를 참조하십시오.
``` python
x = "awesome"

def myfunc():
  global x
  x = "fantastic"

myfunc()

print("Python is " + x)
```

# Reference
[w3schools python](https://www.w3schools.com/python/python_syntax.asp)