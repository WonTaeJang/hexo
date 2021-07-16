---
title: py-day18-iterators
date: 2021-07-16 10:16:57
   - python 
   - iterators
categories: 
   - python-iterators
---

# Python Iterators (반복자)
반복자는 셀 수 있는 값을 포함하는 개체입니다.

반복자는 반복될 수 있는 개체입니다. 즉, 모든 값을 순회할 수 있습니다.

&#95;&#95;iter&#95;&#95;() , &#95;&#95;next&#95;&#95;()

> An iterator is an object that contains a countable number of values.

> An iterator is an object that can be iterated upon, meaning that you can traverse through all the values.

> Technically, in Python, an iterator is an object which implements the iterator protocol, which consist of the methods __iter__() and __next__().

## 1. Iterator vs Iterable
Lists, tuples, dictionaries, sets 들이 반복가능(Iterable) 객체이다.
반복자(Iterator)를 얻을 수 있는 반복 가능한(Iterable) 컨테이너 입니다.

이러한 객체들은 반복자를 얻는데 사용되는 iter() 메소드를 가지고 있습니다. 

> Lists, tuples, dictionaries, and sets are all iterable objects. They are iterable containers which you can get an iterator from.

> All these objects have a iter() method which is used to get an iterator

### example
``` python
mytuple = ("apple", "banana", "cherry")
myit = iter(mytuple)

print(next(myit))
print(next(myit))
print(next(myit))
```

문자열조차도 반복 가능한 객체이며 반복자를 반환할 수 있습니다.

### example
``` python
mystr = "banana"
myit = iter(mystr)

print(next(myit))
print(next(myit))
print(next(myit))
print(next(myit))
print(next(myit))
print(next(myit))
```

## 2. Looping Through an Iterator
for loop를 이용하여 반복 가능한 객체를 반복 할 수도 있습니다.

### example
``` python
mytuple = ("apple", "banana", "cherry")

for x in mytuple:
  print(x)
```

### example
``` python
mystr = "banana"

for x in mystr:
  print(x)
```

## 3. Create an Iterator
Object/Class 반복자를 만들기 위해서는 &#95;&#95;iter&#95;&#95;() , &#95;&#95;next&#95;&#95;() 메소드를 구현하여야 한다.

&#95;&#95;iter&#95;&#95;(): 항상 반복자 개체 자체를 반환해야 합니다.

&#95;&#95;next&#95;&#95;(): 작업을 수행할 수 있으며 시퀀스의 다음 항목을 반환해야 합니다.  

To create an object/class as an iterator you have to implement the methods &#95;&#95;iter&#95;&#95;() and &#95;&#95;next&#95;&#95;() to your object.

### example
``` python
class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self

  def __next__(self):
    x = self.a
    self.a += 1
    return x

myclass = MyNumbers()
myiter = iter(myclass)

print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
```

## 4. StopIteration(반복 중지)
반복이 영원히 계속되는 것을 방지하기 위해 StopIteration명령문을 사용할 수 있습니다 .

### example
``` python
class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self

  def __next__(self):
    if self.a <= 20:
      x = self.a
      self.a += 1
      return x
    else:
      raise StopIteration

myclass = MyNumbers()
myiter = iter(myclass)

for x in myiter:
  print(x)
```

# Reference
[w3schools python](https://www.w3schools.com/python)