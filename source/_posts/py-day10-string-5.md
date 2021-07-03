---
title: py-day10-string-5
date: 2021-07-03 17:30:49
    - python 
    - string
    - format
categories: 
    - python
---

# 문자열 형식 (String Format)
변수 챕터에서 배웠 듯이 문자열과 숫자를 결합할 수 없습니다.

### example
``` python
age = 36
txt = "My name is John, I am " + age
print(txt) # TypeError
```

format() method를 사용하여 숫자와 문자를 결합할 수 있습니다. 

### example
``` python
ge = 36
txt = "My name is John, and I am {}"
print(txt.format(age))
```

format() method는 숫자인수를 무제한 입력 할 수 있습니다. 
> The format() method takes unlimited number of arguments, and are placed into the respective placeholders

### example
``` python
quantity = 3
itemno = 567
price = 49.95
myorder = "I want {} pieces of item {} for {} dollars."
print(myorder.format(quantity, itemno, price))
```

index number {0}를 사용하여 인수의 자리 위치를 표시할 수 있습니다.
>You can use index numbers {0} to be sure the arguments are placed in the correct placeholders

### example
``` python
quantity = 3
itemno = 567
price = 49.95
myorder = "I want to pay {2} dollars for {0} pieces of item {1}."
print(myorder.format(quantity, itemno, price))
```

# Exercises
[py-exercises-3](https://wontaejang.github.io/2021/07/03/py-exercises-4/)

# Reference
[w3schools python](https://www.w3schools.com/python)