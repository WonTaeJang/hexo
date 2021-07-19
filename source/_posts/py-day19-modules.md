---
title: py-day19-modules
date: 2021-07-19 10:16:16
   - python 
   - modules
categories: 
   - python-modules
---

# Python Modules
## What is a Module?
Module은 Code Library와 동일하다.

응용 프로그램에 포함하려는 함수들의 집합이 포함된 파일입니다.

> Consider a module to be the same as a code library.

> A file containing a set of functions you want to include in your application.

## 1. Create a Module
Mobule을 만들기 위해서는 .py 확장자로 파일을 생성하면 된다.
> To create a module just save the code you want in a file with the file extension .py

### example
Save this code in a file named mymodule.py
``` python
def greeting(name):
  print("Hello, " + name)
```

## 1.1 Use a Module
import 문을 사용하여 module을 사용할 수 있습니다. 

> Now we can use the module we just created, by using the import statement

### example
``` python
import mymodule

mymodule.greeting("Jonathan")
```

> Note: When using a function from a module, use the syntax: module_name.function_name.

## 2. Variables in Module
module은 함수를 포함 할 수 있고, 모든 타입의 변수도 포함할 수 있다.

> The module can contain functions, as already described, but also variables of all types (arrays, dictionaries, objects etc)

### example
Save this code in the file mymodule.py
``` python
person1 = {
  "name": "John",
  "age": 36,
  "country": "Norway"
}
```

### example
``` python
import mymodule

a = mymodule.person1["age"]
print(a)
```

## 3. Naming a Module
Module 명은 원하는데로 수정이 가능하지만 확장자는 .py를 지켜야 한다.

## 3.1 Re-naming a Module
import module의 명을 as 키워드를 사용하여 바꿀 수 있다. 

### example
``` python
import mymodule as mx

a = mx.person1["age"]
print(a)
```

## 4. Built-in Modules (내장된 모듈)
### example
``` python
import platform

x = platform.system()
print(x)
```

## 4.1 Using the dir() Function
dir() 함수를 사용하면 모듈의 내장된 함수를 확인할 수 있다.

> There is a built-in function to list all the function names (or variable names) in a module. The dir() function:

### example
``` python
import platform

x = dir(platform)
print(x)
```

## 5. Import From Module
from 키워드를 사용하여 Module에 일부분만 가져올 수 있다. 

### example
``` python
# mymodule.py
def greeting(name):
  print("Hello, " + name)

person1 = {
  "name": "John",
  "age": 36,
  "country": "Norway"
}
```

### example
``` python
from mymodule import person1

print (person1["age"])
```

# Reference
[w3schools python](https://www.w3schools.com/python)