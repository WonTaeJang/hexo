---
title: py-day16-class-object
date: 2021-07-09 11:34:02
   - python 
   - class
   - object
categories: 
   - python-object
---

# Python Classes/Objects
- Python은 객체지향 언어이다. 
- Python의 대부분이 properties와 method가 있는 object이다. 
- 클래스는 객체 생성자 또는 객체 생성을 위한 "청사진"과 같습니다.

>- Python is an object oriented programming language.
>- Almost everything in Python is an object, with its properties and methods.
>- A Class is like an object constructor, or a "blueprint" for creating objects.

## 정의
> class : 
> - 실세계의 것을 모델링하여 속성과 동작을 갖는 데이터 타입
>- 다루고자 하는 데이터와 데이터를 다루는 연산을 하나로 캡슐화하여 클래스로 표현

> init(self):
>- 생성자를 정의, 클래스 인스턴스가 생성될 때 호출됨
>- self인자는 항상 첫 번째로 오며 자기 자신을 가리킴

> method: 
>- 멤버함수라고 하며, 해당 클래스의 object에서만 호출 가능

> object: 
>- 객체는 어떠한 속성값과 행동을 가지고 있는 데이터
>- 파이썬의 모든것들(숫자, 문자, 함수 등)은 여러 속성과 행동을 가지고 있는 데이터

## Create a Class
class 키워드를 사용하여 클래스를 만들어봅시다. 

### example
``` python
class MyClass:
  x = 5
```

## Create Object
선언한 클래스를 사용하여 object를 생성하여 봅시다. 

### example
``` python
p1 = MyClass()
print(p1.x)
```

## &#95;&#95;init&#95;&#95;() Function
- &#95;&#95;init&#95;&#95;()는 클래스가 시작할때 항상 실행되는 함수이다.
- &#95;&#95;init&#95;&#95;() 함수를 사용하여 객체 속성에 값을 할당하거나 객체를 생성할 때 수행해야 하는 기타 작업을 수행합니다.

### example
Create a class named Person, use the &#95;&#95;init&#95;&#95;() function to assign values for name and age:
``` python
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

p1 = Person("John", 36)

print(p1.name)
print(p1.age)
```

## Object Methods
- Object는 methods를 가질 수 있습니다. 

- object methods는 object에 속하는 함수입니다. 

### example
``` python
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def myfunc(self):
    print("Hello my name is " + self.name)

p1 = Person("John", 36)
p1.myfunc()
```

## self Parameter
self 파라메터는 현재의 클래스 인스턴스를 참조하고, 클래스에 속한 변수를 접근하여 사용한다. 

self라고 이름지어질 필요가 없으며 원하는 명으로 지을 수 있다. 그러나 첫번째 파라메터로 지정하여야 한다 

>The self parameter is a reference to the current instance of the class, and is used to access variables that belongs to the class.

>It does not have to be named self , you can call it whatever you like, but it has to be the first parameter of any function in the class:

## Modify Object Properties
### example
``` python
p1 = testClass()
p1.age = 40
```

## Delete Object Properties
### example
``` python
p1 = testClass()
del p1.age
```

## Delete Objects
### example
``` python
p1 = testClass()
del p1
```

## The pass Statement
### example
``` python
class Person:
  pass
```
# Exercises
[py-exercises-12](https://wontaejang.github.io/2021/07/13/py-exercises-12/)

# Reference
[w3schools python](https://www.w3schools.com/python)