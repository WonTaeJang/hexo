---
title: py-day13-if
date: 2021-07-06 10:02:55
   - python 
   - if
categories: 
   - python-if
---

# Python IF...Else
## 조건문과 If문
Python에서는 수학적인 논리 조건을 지원한다. 
 - Equals: a == b
 - Not Equals: a != b
 - Less than: a < b
 - Less than or equal to: a <= b
 - Greater than: a > b
 - Greater than or equal to: a >= b

이러한 조건문은 보통 if문이나 Loop에 사용된다. 

### example
``` python
a = 33
b = 200
if b > a:
  print("b is greater than a")
```

### example
들여쓰기를 하지않으면 오류가 발생:
``` python
a = 33
b = 200
if b > a:
print("b is greater than a")
```

## Elif
앞선 조건이 충족하지 않으면 이 elif로 시도한다. 
>The elif keyword is pythons way of saying "if the previous conditions were not true, then try this condition".

### example
``` python
a = 33
b = 33
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
```

## else
앞의 모든 조건이 충족하지 않으면 해당 키워드에서 실행된다.

### example
``` python
a = 200
b = 33
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
else:
  print("a is greater than b")
```

elif 없이도 사용이 가능하다.
### example
``` python
a = 200
b = 33
if b > a:
  print("b is greater than a")
else:
  print("b is not greater than a")
```

## Short Hand If
### example
One line if statement:
``` python
if a > b: print("a is greater than b")
```

## Short Hand If ... Else
### example
One line if else statement:
``` python
a = 2
b = 330
print("A") if a > b else print("B")
```

## And
and 키워드는 논리 연산자로 조건문을 조합할때 사용된다.
### example
``` python
a = 200
b = 33
c = 500
if a > b and c > a:
  print("Both conditions are True")
```

## OR
or 키워드는 논리 연산자로 조건문을 조합할때 사용된다.
### example
``` python
a = 200
b = 33
c = 500
if a > b or a > c:
  print("At least one of the conditions is True")
```

## if문 중첩
### example
``` python
x = 41

if x > 10:
  print("Above ten,")
  if x > 20:
    print("and also above 20!")
  else:
    print("but not above 20.")
```

## pass문
if문을 선언하고 사용하지 않을경우 pass를 사용하면 된다.
>if statements cannot be empty, but if you for some reason have an if statement with no content, put in the pass statement to avoid getting an error.

### example
``` python
a = 33
b = 200

if b > a:
  pass
```

# Exercises
[py-exercises-8](https://wontaejang.github.io/2021/07/06/py-exercises-8/)

# Reference
[w3schools python](https://www.w3schools.com/python)