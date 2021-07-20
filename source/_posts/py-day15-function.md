---
title: py-day15-function
date: 2021-07-08 10:17:35
   - python 
   - function
categories: 
   - python-function
---

함수는 호출 되었을때 해당 코드 블록이 실행이 된다.      
함수에 매개변수(parameters) 값을 보낼 수 있다.        
함수는 결과값을 return 해준다.      

> A function is a block of code which only runs when it is called.          
>You can pass data, known as parameters, into a function.       
>A function can return data as a result.

## 1. 함수 생성(Creating a Function)
def 키워드로 함수를 정의한다. 

### example
``` python
def my_function():
  print("Hello from a function")
```

## 2. 함수 호출(Calling a Function)
함수를 호출하려면 함수 이름 뒤에 괄호를 사용합니다.

### example
``` python
def my_function():
  print("Hello from a function")

my_function()
```

## 3. 인수 (Arguments)
정보는 인수로 함수에 전달 될수 있습니다.    

인수는 함수 명 뒤에 괄호안에 지정됩니다. 인수는 원하는 만큼 넣을수 있고, ',' 콤마로 분리 됩니다. 

>- Information can be passed into functions as arguments.     
>- Arguments are specified after the function name, inside the parentheses. You can add as many arguments as you want, just separate them with a comma.       
>- The following example has a function with one argument (fname). When the function is called, we pass along a first name, which is used inside the function to print the full name:

### example
``` python
def my_function(fname):
  print(fname + " Refsnes")

my_function("Emil")
my_function("Tobias")
my_function("Linus")
```

> Arguments are often shortened to args in Python documentations.

## 4. 매개변수(Parameters) or 인수(Arguments)?
함수에 정보를 전달하는데 있어서 매개변수와 인수는 같은 의미입니다. 
> The terms parameter and argument can be used for the same thing: information that are passed into a function

## 5. Number of Arguments
기본적으로 함수는 인수값을 일치시켜 사용해야합니다. 
>By default, a function must be called with the correct number of arguments. Meaning that if your function expects 2 arguments, you have to call the function with 2 arguments, not more, and not less.

### example
``` python
def my_function(fname, lname):
  print(fname + " " + lname)

my_function("Emil", "Refsnes")
```

> If you try to call the function with 1 or 3 arguments, you will get an error:

### example
This function expects 2 arguments, but gets only 1:
``` python
def my_function(fname, lname):
  print(fname + " " + lname)

my_function("Emil")
```

## 6. 임의의 인수, * args
함수에 전달 될 인수의 수를 모르는 *경우 함수 정의에서 매개 변수 이름 앞에를 추가하십시오.

이렇게하면 함수가 인수 튜플 을 수신하고 그에 따라 항목에 액세스 할 수 있습니다.

### example
``` python
def my_function(*kids):
  print("The youngest child is " + kids[2])

my_function("Emil", "Tobias", "Linus")
```

임의 인수 는 종종 Python 문서에서 * args 로 축약됩니다.
> Arbitrary Arguments are often shortened to *args in Python documentations.

## 7. 키워드 인수(Keyword Arguments)
key = value 방식으로 사용할 수 있으면 이경우 인수의 순서가 중요하지 않습니다.

You can also send arguments with the key = value syntax.
This way the order of the arguments does not matter.

### example
``` python
def my_function(child3, child2, child1):
  print("The youngest child is " + child3)

my_function(child1 = "Emil", child2 = "Tobias", child3 = "Linus")
```

> The phrase Keyword Arguments are often shortened to kwargs in Python documentations.

## 8. 임의의 키워드 인수, **kwargs
얼마나 많은수의 키워드 인수가 함수에 들어올 지 알수 없을때 사용되는 방식입니다. 

이방식은 함수가 dictionary 인수를 받고 items에 접근합니다. 
> If you do not know how many keyword arguments that will be passed into your function, add two asterisk: ** before the parameter name in the function definition.

> This way the function will receive a dictionary of arguments, and can access the items accordingly

### example
``` python
def my_function(**kid):
  print("His last name is " + kid["lname"])

my_function(fname = "Tobias", lname = "Refsnes")
```

## 9. Default Parameter Value
함수를 정의할 때 매개변수에 기본값을 설정하면 함수를 호출할때 인수없이도 호출이 가능하다.

### example
``` python
def my_function(country = "Norway"):
  print("I am from " + country)

my_function("Sweden")
my_function("India")
my_function()
my_function("Brazil")
```

## 10. 리스트 목록을 전달(Passing a List as an Argument)
string, number, list, dictionart 등등의 data type을 함수의 인수로 전달 할 수 있습니다.

> You can send any data types of argument to a function (string, number, list, dictionary etc.), and it will be treated as the same data type inside the function

### example
``` python
def my_function(food):
  for x in food:
    print(x)

fruits = ["apple", "banana", "cherry"]

my_function(fruits)
```

## 11. Return Values
함수에서 값이 반환되게 할려면 Return문을 작성하여야 합니다.

> To let a function return a value, use the return statement

### example
``` python
def my_function(x):
  return 5 * x

print(my_function(3))
print(my_function(5))
print(my_function(9))
```

## 12. The pass Statement
> function definitions cannot be empty, but if you for some reason have a function definition with no content, put in the pass statement to avoid getting an error

### example
``` python
def myfunction():
  pass
```

## 13. 재귀 함수(Recursion)
재귀함수는 함수가 자기자신을 호출하는것을 의미한다.
> Python also accepts function recursion, which means a defined function can call itself.

>Recursion is a common mathematical and programming concept. It means that a function calls itself. This has the benefit of meaning that you can loop through data to reach a result.

>The developer should be very careful with recursion as it can be quite easy to slip into writing a function which never terminates, or one that uses excess amounts of memory or processor power. However, when written correctly recursion can be a very efficient and mathematically-elegant approach to programming.

>In this example, tri_recursion() is a function that we have defined to call itself ("recurse"). We use the k variable as the data, which decrements (-1) every time we recurse. The recursion ends when the condition is not greater than 0 (i.e. when it is 0).

>To a new developer it can take some time to work out how exactly this works, best way to find out is by testing and modifying it.

### example
``` python
def tri_recursion(k):
  if(k > 0):
    result = k + tri_recursion(k - 1)
    print(result)
  else:
    result = 0
  return result

print("\n\nRecursion Example Results")
tri_recursion(6)
```
# Exercises
[py-exercises-11](https://wontaejang.github.io/2021/07/08/py-exercises-11/)

# Reference
[w3schools python](https://www.w3schools.com/python)