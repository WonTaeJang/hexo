---
title: py-day10-string-3
date: 2021-07-03 17:20:28
    - python 
    - string
categories: 
    - python
---

# 문자열 수정 (Modify Strings)
Python에는 문자열에 사용할 수 있는 내장 함수들이 있습니다.

## 1. 대문자(Upper Case)
### example
``` python
a = "Hello, World!"
print(a.upper())    # "HELLO, WORLD!"
```

## 2. 소문자(Lower Case)
### example
``` python
a = "Hello, World!"
print(a.lower())    # "hello, world!"
```

## 3. 공백 제거(Remove Whitespace)
공백제거는 문자열의 앞뒤의 공백을 제거해줍니다. 
### example
``` python
a = " Hello, World! "
print(a.strip()) # returns "Hello, World!"
```

## 4. 문자열 대체(Replace String)
### example
``` python
a = "Hello, World!"
print(a.replace("H", "J"))  # "Jello, World!"
```

## 5. 문자열 분리(Split String)
### example
``` python
a = "Hello, World!"
print(a.split(",")) # returns ['Hello', ' World!']
```

# Reference
[w3schools python](https://www.w3schools.com/python)