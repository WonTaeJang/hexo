---
title: py-exercises-13
date: 2021-07-15 11:08:21
    - python 
    - inheritance
    - exercises
categories: 
    - python-inheritance
---

# Exercise 1

``` python
class Person:
  def __init__(self, fname):
    self.firstname = fname

  def printname(self):
    print(self.firstname)

class Student(Person):
  pass
```

## Exercise 1.1
변수 x 에 student 클래스를 선언하여 "Miss Fortune" 을 생성자로 넣어 보시오.

## Exercise 1.2
변수 x 를 통해 printname을 사용하여 보시오. 

# Exercise 2

``` python
class LOL:
  def __init__(self, fname):
    self.name = fname

  def printname(self):
    print(self.name)

class Champion(LOL):
  ???
```

## Exercise 2.1
Champion 클래스에 setLevel 메소드를 만들어 Level 을 입력할 수 있게 하시오.

## Exercise 2.2
Champion 클래스에 getState 메소드를 만들어 아래와 같이 출력할 수 있게 하시오.
``` code
name: Miss Fortune
LV: 10
```