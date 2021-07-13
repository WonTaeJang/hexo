---
title: py-day9-numbers
date: 2021-07-03 15:44:21
    - python 
    - numbers
categories: 
    - python-numbers
---

# Python Numbers
파이썬은 숫자형 타입이 3개 있습니다. 
- int
- float
- complex

숫자형 타입으로 변수를 생성하고 싶다면 아래의 예제와 같이 값을 할당하면 됩니다. 

### example
``` python
x = 1    # int
y = 2.8  # float
z = 1j   # complex
```

숫자형 타입을 할당한 변수의 데이터 타입을 확인하고 싶다면 type() 함수를 이용하시면 됩니다. 

### example
``` python
print(type(x))
print(type(y))
print(type(z))
```

## 1. int
int, or integer는 숫자, 정수(음수, 양수)

>Int, or integer, is a whole number, positive or negative, without decimals, of unlimited length.

### example
Integers:
``` python
x = 1
y = 35656222554887711
z = -3255522

print(type(x))
print(type(y))
print(type(z))
```

## 2. float
float, or "floating point number", 실수
>Float, or "floating point number" is a number, positive or negative, containing one or more decimals.

### example
Floats:
``` python
x = 1.10
y = 1.0
z = -35.59

print(type(x))
print(type(y))
print(type(z))
```

Float는 10의 거듭 제곱을 나타내는 "e"가있는 과학적 숫자 일 수도 있습니다.

### example
Floats:
``` python
x = 35e3
y = 12E4
z = -87.7e100

print(type(x))
print(type(y))
print(type(z))
```

## 3. complex
complex는 허수
>Complex numbers are written with a "j" as the imaginary part

### example
Complex:
``` python
x = 3+5j
y = 5j
z = -5j

print(type(x))
print(type(y))
print(type(z))
```

## 4. 타입 변환(Type Conversion)
int(), float(), complex() 함수를 이용하여 숫자타입을 바꿀 수 있습니다. 
>You can convert from one type to another with the int(), float(), and complex() methods

### example
타입 변환:
``` python
x = 1    # int
y = 2.8  # float
z = 1j   # complex

#convert from int to float:
a = float(x)

#convert from float to int:
b = int(y)

#convert from int to complex:
c = complex(x)

print(a)
print(b)
print(c)

print(type(a))
print(type(b))
print(type(c))
```

complex 타입은 다른 숫자타입으로 변환할 수 없습니다.
>Note: You cannot convert complex numbers into another number type.

## 5. Random Number
Python은 random() 함수가 없어서 랜덤숫자를 만들 수 없습니다. 그래서 Python은 random 이라는 내장 모듈을 불러와 사용할 수 있습니다. 
>  Python does not have a random() function to make a random number, but Python has a built-in module called random that can be used to make random numbers:

### example
랜덤 모듈을 import 하여 1~9 사이의 숫자를 랜덤하게 출력:
>Import the random module, and display a random number between 1 and 9:
``` python
import random

print(random.randrange(1, 10))
```

> Random Module이 궁금하다면 다음 챕터에서 배울 수 있습니다.

# Exercises
[py-exercises-3](https://wontaejang.github.io/2021/07/03/py-exercises-3/)

# Reference
[w3schools python](https://www.w3schools.com/python/python_syntax.asp)