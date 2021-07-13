---
title: py-day10-string-1
date: 2021-07-03 16:18:36
    - python 
    - string
categories: 
    - python-string
---

# Python String
## 1. 문자열(strings)
- 파이썬의 문자열은 작은 따옴표 또는 큰 따옴표로 묶여 있습니다.
- 'hello' 는 "hello" 와 동일 합니다.
- print()함수를 사용하여 문자열 리터럴을 표시 할 수 있습니다 .

### example
``` python
print("Hello")
print('Hello')
```
## 2. 변수에 문자열 할당
> Assigning a string to a variable is done with the variable name followed by an equal sign and the string:

### example
``` python
a = "Hello"
print(a)
```

## 3. 여러줄 문자열 (Multiline Strings)
""" 를 이용하여 여러줄 문자열을 변수에 할당할 수 있습니다.
### example
``` python
a = """Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua."""
print(a)
```

or 3개의 작은 따옴표로도 표현 가능

``` python
a = '''Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua.'''
print(a)
```

## 4. 문자열의 배열 (Strings are Arrays)
- Python의 문자열은 유니코드 문자를 나타내는 바이트 배열입니다. 

- Python에는 character data type이 없으며 single character는 단순히 길이가 1 인 문자열입니다.

- 대괄호를 사용하여 문자열의 요소에 접근할 수 있습니다.

### example
문자열의 첫번째 배열은 0부터입니다.
>Get the character at position 1 (remember that the first character has the position 0)
``` python
a = "Hello, World!"
print(a[1])
```

## 5. 문자열을 통한 Loop
문자열은 배열이기 때문에 for Loop를 사용하여 문자열의 문자를 반복할 수 있습니다.

### example
``` python
for x in "banana":
  print(x)
```
> For Loop는 다음 챕터에서 다루겠습니다.

## 6. 문자열 길이(String Length)
문자열 길이를 얻기위해서는 len() 함수를 사용하면 됩니다.

### example
len() 함수는 문자열의 길이를 반환해 줍니다.
> The len() function returns the length of a string:
``` python
a = "Hello, World!"
print(len(a))
```

## 7. 문자열 확인(Check String)
in 키워드를 이용하여 해당 문자열이 존재하는지 확인할 수 있다.
>To check if a certain phrase or character is present in a string, we can use the keyword in.

### example
txt 변수에 "free"가 있는지 확인하십시오.
``` python
txt = "The best things in life are free!"
print("free" in txt)
```

if 문을 사용한 in 키워드
### example
``` python
txt = "The best things in life are free!"
if "free" in txt:
  print("Yes, 'free' is present.")
```
> if...else 문은 다음 챕터에서 다루겠습니다.

## 8. 문자열 있지 않은지 확인(Check if NOT)
해당 문자가 존재하지 않은지 확인할때는 not in 키워드를 이용하면 된다.
>To check if a certain phrase or character is NOT present in a string, we can use the keyword not in.

### example
``` python
txt = "The best things in life are free!"
print("expensive" not in txt)
```

if 문을 사용한 not in 키워드
### example
``` python
txt = "The best things in life are free!"
if "expensive" not in txt:
  print("Yes, 'expensive' is NOT present.")
```

# Reference
[w3schools python](https://www.w3schools.com/python)