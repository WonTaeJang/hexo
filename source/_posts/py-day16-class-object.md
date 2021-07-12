---
title: py-day16-class-object
date: 2021-07-09 11:34:02
   - python 
   - class
   - object
categories: 
   - python
---

# Python Classes/Objects
- Python은 객체지향 언어이다. 
- Python의 대부분이 properties와 method가 있는 object이다. 
- 클래스는 객체 생성자 또는 객체 생성을 위한 "청사진"과 같습니다.

>- Python is an object oriented programming language.
>- Almost everything in Python is an object, with its properties and methods.
>- A Class is like an object constructor, or a "blueprint" for creating objects.

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

# Reference
[w3schools python](https://www.w3schools.com/python)