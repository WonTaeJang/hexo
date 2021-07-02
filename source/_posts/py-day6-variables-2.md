---
title: py-day6-variables-2
date: 2021-07-02 09:36:35
    - python 
    - variables
    - output
categories: 
    - python
---

# Python Variables 2
변수(Varialble)	값이 저장된 메모리 공간의 주소를 가르키는 식별자(identifier)

## 1. 변수 명
변수 명은 짧게 지을수도 있고 상세하게 지을수도 있습니다. Python 변수 명에 대한 규칙: 
- 변수 명은 문자 또는 '_' 로 시작해야 합니다. (ex sort, _sort)
- 변수 명은 숫자로 시작할 수 없습니다.
- 변수 명에는 영숫자 문자와 밑줄 (Az, 0-9 및 _) 만 포함 할 수 있습니다. (한글도 가능) 
- 변수 이름은 대소 문자를 구분합니다.

### example
``` python
myvar = "John"
my_var = "John"
_my_var = "John"
myVar = "John"
MYVAR = "John"
myvar2 = "John"
```

### example
잘못된 변수 이름:
``` python
2myvar = "John"
my-var = "John"
my var = "John"
```

## 2. 여러 단어로 변수명 짓기
둘 이상의 단어가 포함된 변수 명은 읽기 어려울수 있습니다. 
여러 단어가 들어간 변수 명을 읽기 쉽게 만드는 기술을 소개합니다. 

### Camel Case
첫 번째 단어를 제외한 각 단어는 대문자로 시작합니다.
``` Python
myVariableName = "John"
```

### Pascal Case
각 단어는 대문자로 시작합니다.
``` Python
MyVariableName = "John"
```

### Snake Case
각 단어는 밑줄 문자로 구분됩니다.
``` Python
my_variable_name = "John"
```

## 3. 여러 값 활당 (Assign Multiple Values)
Python을 사용하면 한 줄로 여러 변수에 값을 할당 할 수 있습니다.

### example
잘못된 변수 이름:
``` python
x, y, z = "Orange", "Banana", "Cherry"
print(x)
print(y)
print(z)
```
> 참고: 변수 수가 값의 수와 일치하지 않으면 오류 발생

## 4. 여러 변수에 대한 하나의 값 (One Value to Multiple Variables)
한 줄에 여러 변수에 동일한 값을 할당 할 수 있습니다 .

### example
잘못된 변수 이름:
``` python
x = y = z = "Orange"
print(x)
print(y)
print(z)
```

## 5. Unpack a Collection
list, tuple등의 collection이 있을 경우 Python을 사용하면 변수로 추출 할 수 있습니다. 이것을 Unpack이라고 합니다.

### example
``` python
fruits = ["apple", "banana", "cherry"]
x, y, z = fruits
print(x)
print(y)
print(z)
```
> Unpack Tuples 챕터에서 Unpack에 대해서 더 자세히 알아보겠습니다.


## 6. 변수 출력
Python print문은 종종 변수를 출력하는 데 사용됩니다.
텍스트와 변수를 결합하기 위해 Python은 다음 + 문자를 사용합니다.

### example
``` python
x = "awesome"
print("Python is " + x)
```

+문자를 사용하여 다른 변수에 변수를 추가 할 수도 있습니다.

### example
``` python
x = 5
y = 10
print(x + y)
```

문자열과 숫자를 결합하려고하면 Python에서 오류가 발생합니다.
### example
``` python
x = 5
y = "John"
print(x + y)
```

# Reference
[w3schools python](https://www.w3schools.com/python/python_syntax.asp)