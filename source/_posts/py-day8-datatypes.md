---
title: py-day8-datatypes
date: 2021-07-02 10:46:21
    - python 
    - datatype
categories: 
    - python-datatypes
---

# Python DataTypes
## 1. 내장 되어 있는 데이터 타입(Built-in Data Types)
프로그래밍에서 데이터 유형은 중요한 개념입니다.

변수는 다른 유형의 데이터를 저장할 수 있으며 다른 유형은 다른 일을 할 수 있습니다.

Python에는 기본적으로 다음과 같은 카테고리에 다음 데이터 유형이 내장되어 있습니다.

||data type|
|------|-------|
|Text Type|str|
|Numeric Types|int, float, complex|
|Sequence Types|list, tuple, range|
|Mapping Type|dict|
|Set Types|set, frozenset|
|Boolean Type|bool|
|Binary Types|bytes, bytearray, memoryview|

## 2. 데이터 타입을 확인해 봅시다.
type()함수 를 사용하여 모든 개체의 데이터 유형을 가져올 수 있습니다.

### example
``` python
x = 5
print(type(x))
```

## 3. 데이터 타입 설정
Python에서는 변수에 값을 할당 할 때 데이터 유형이 설정됩니다.

|Example|Data Type|
|-------|---------|
|x = "Hello World"|str|
|x = 20|int|
|x = 20.5|float|
|x = 1j|complex|
|x = ["apple", "banana", "cherry"]|list|
|x = ("apple", "banana", "cherry")|tuple|
|x = range(6)|range|
|x = {"name" : "John", "age" : 36}|dict|
|x = {"apple", "banana", "cherry"}|set|
|x = frozenset({"apple", "banana", "cherry"})|frozenset|
|x = True|bool|
|x = b"Hello"|bytes|
|x = bytearray(5)|bytearray|
|x = memoryview(bytes(5))|memoryview|

## 4. 특정 데이터 타입 설정
데이터 유형을 지정하려는 경우 다음 생성자 함수를 사용할 수 있습니다.

|Example|Data Type|
|-------|---------|
|x = str("Hello World")|str|
|x = int(20)|int|
|x = float(20.5)|float|
|x = complex(1j)|complex|
|x = list(("apple", "banana", "cherry"))|list|
|x = tuple(("apple", "banana", "cherry"))|tuple|
|x = range(6)|range|
|x = dict(name="John", age=36)|dict|
|x = set(("apple", "banana", "cherry"))|set|
|x = frozenset({"apple", "banana", "cherry"})|frozenset|
|x = bool(5)|bool|
|x = bytes(5)|bytes|
|x = bytearray(5)|bytearray|
|x = memoryview(bytes(5))|memoryview|

# Reference
[w3schools python](https://www.w3schools.com/python/python_syntax.asp)