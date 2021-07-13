---
title: py-day10-string-2
date: 2021-07-03 16:55:39
    - python 
    - string
    - slicing
categories: 
    - python-string
---

# Python String 2
## 1. Slicing 
slice syntax를 이용하여 문자열을 자를수 있습니다. 

### example
문자열에서 2 ~ 5번째 (마지막은 미포함)를 얻습니다.
``` python
b = "Hello, World!"
print(b[2:5])
```

### example
문자열 배열에서 0 ~ 5번째 (마지막은 미포함)를 얻습니다.
``` python
b = "Hello, World!"
print(b[:5])
```

### example
문자열 배열에서 0 ~ 마지막을 얻습니다.
``` python
b = "Hello, World!"
print(b[2:])
```

### example
문자열 배열에서 -5 ~ -2번째 (마지막은 미포함)를 얻습니다.
``` python
b = "Hello, World!"
print(b[-5:-2])
```

# Reference
[w3schools python](https://www.w3schools.com/python)