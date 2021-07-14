---
title: py-day17-inheritance
date: 2021-07-14 10:45:17
   - python 
   - inheritance
categories: 
   - python-inheritance
---

# Python Inheritance
상속을 통해 다른 클래스의 모든 메서드와 속성을 상속하는 클래스를 정의할 수 있습니다.

Parent class 는 상속되는 클래스 이며 base class 라고도 합니다.

Child class 는 파생 클래스라고도 하는 다른 클래스에서 상속되는 클래스입니다.

>Inheritance allows us to define a class that inherits all the methods and properties from another class.

>Parent class is the class being inherited from, also called base class.

>Child class is the class that inherits from another class, also called derived class.

## 1. Create a Parent Class
부모 클래스는 일반 클래스와 동일합니다. 기본 클래스 생성과 똑같습니다.

>Any class can be a parent class, so the syntax is the same as creating any other class

### example
``` python
class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)

#Use the Person class to create an object, and then execute the printname method:

x = Person("John", "Doe")
x.printname()
```

## 2. Create a Child Class
다른 클래스의 기능을 상속하는 클래스를 만들려면 자식 클래스를 만들 때 부모 클래스를 매개 변수로 보냅니다.

> To create a class that inherits the functionality from another class, send the parent class as a parameter when creating the child class

### example
Student 클래스를 생성하여 Person 클래스 속성과 메서드를 상속하게 만듭니다.
``` python
class Student(Person):
  pass
```

>Note: Use the pass keyword when you do not want to add any other properties or methods to the class.

Student 클래스는 Person 클래스의 속성과 메소드를 가진 클래스가 된다.
>Now the Student class has the same properties and methods as the Person class.

### example
``` python
x = Student("Mike", "Olsen")
x.printname()
```

## 3. Add the __init__() Function
자식 클래스에 생성자 함수를 만들어 봅시다.

> So far we have created a child class that inherits the properties and methods from its parent.

>We want to add the &#95;&#95;init&#95;&#95;() function to the child class (instead of the pass keyword).


note: &#95;&#95;init&#95;&#95;()함수는 클래스를 사용하여 새 개체를 만들 때마다 자동으로 호출됩니다

> Note: The &#95;&#95;init&#95;&#95;() function is called automatically every time the class is being used to create a new object.

### example
``` python
class Student(Person):
  def __init__(self, fname, lname):
    #add properties etc.
```

자식 클래스에서 &#95;&#95;init&#95;&#95;() 함수를 넣게되면 더이상 부모 클래스의 &#95;&#95;init&#95;&#95;() 함수를 상속받지 않습니다. 

> When you add the __init__() function, the child class will no longer inherit the parent's __init__() function.

자식 클래스에서 부모 클래스의 &#95;&#95;init&#95;&#95;() 함수를 상속받고 싶다면 부모 클래스의 &#95;&#95;init&#95;&#95;() 함수를 호출하면 된다.
> To keep the inheritance of the parent's __init__() function, add a call to the parent's __init__() function

### example
``` python
class Student(Person):
  def __init__(self, fname, lname):
    Person.__init__(self, fname, lname)
```