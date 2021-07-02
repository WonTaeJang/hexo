---
title: py-day2-syntax-1
date: 2021-07-01 10:53:40
    - python 
    - syntax
categories: 
    - python
---

# Python Syntax 1
## 들여쓰기
들여쓰기는 코드 줄의 시작 부분에 있는 공백을 나타냅니다. 
다른 프로그래밍 언어에서는 코드의 들여쓰기는 가독성만을 위한 것이지만 Python의 들여쓰기는 매우 중요합니다. 
파이썬은 들여쓰기를 사용하여 **코드블록** 을 나타냅니다.

### Example
``` python
if 5 > 2:
    print("Five is greater than two!")


# Syntax Error
if 5 > 2:
print("Five is greater than two!")
```

공백의 수는 프로그래머에게 달려있지만 적어도 하나는 있어야합니다.

### Example
``` python
if 5 > 2:
 print("Five is greater than two!") 
if 5 > 2:
        print("Five is greater than two!") 
```

동일한 코드 블록에서 동일한 수의 공백을 사용해야합니다. 
### Example
``` python
if 5 > 2:
 print("Five is greater than two!")
        print("Five is greater than two!")
```


# Reference
[w3schools python](https://www.w3schools.com/python/python_syntax.asp)