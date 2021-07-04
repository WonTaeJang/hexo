---
title: py-day11-operators
date: 2021-07-04 12:34:55
    - python 
    - operators
categories: 
    - python
---

# Python 연산자 (Python Operators)
연산자는 변수와 값에 대한 작업을 수행하는 데 사용됩니다.

아래 예제를 보면 +연산자를 사용하여 두 값을 더합니다.

### example
``` python
print(10 + 5)
```

Python은 연산자를 다음 그룹으로 나눕니다.
- 산술 연산자(Arithmetic operators)
- 할당 연산자(Assignment operators)
- 비교 연산자(Comparison operators)
- 논리 연산자(Logical operators)
- Identity operators
- Membership operators
- Bitwise operators

## 1. 산술 연산자(Arithmetic Operators)
산술 연산자는 일반적인 수학 연산을 수행하기 위해 숫자 값과 함께 사용됩니다.

|Operator|Name|Example|
|--------|----|-------|
|+ |    Addition |	x + y|	
|- |    Subtraction |	x - y|	
|* |	Multiplication |	x * y|	
|/ |	Division |	x / y	|
|% |	Modulus |	x % y	|
|** |	Exponentiation |	x ** y|	
|// |	Floor division |	x // y|

## 2. 할당 연산자 (Assignment operators)
할당 연산자는 변수에 값을 할당하는 데 사용됩니다.

|Operator|	Example|	Same As|
|--------|---------|-----------|
|=|	x = 5|	x = 5	|
|+=|	x += 3|	x = x + 3|	
|-=|	x -= 3|	x = x - 3|	
|*=|	x *= 3|	x = x * 3|	
|/=|	x /= 3|	x = x / 3|	
|%=|	x %= 3|	x = x % 3|	
|//=|	x //= 3|	x = x // 3|	
|**=|	x **= 3|	x = x ** 3|	
|&=|	x &= 3|	x = x & 3	|
|&#124;=|	x &#124;= 3|	x = x &#124; 3	|
|^=|	x ^= 3|	x = x ^ 3	|
|>>=|	x >>= 3|	x = x >> 3|	
|<<=|	x <<= 3|	x = x << 3|

## 3. 비교 연산자(Comparison operators)
비교 연산자는 두 값을 비교하는 데 사용됩니다.
|Operator|	Name|	Example|
|--------|------|----------|
|==|	Equal|	x == y	|
|!=|	Not equal|	x != y	|
|>|	Greater than|	x > y	|
|<|	Less than|	x < y	|
|>=|	Greater than or equal to|	x >= y	|
|<=	|Less than or equal to|	x <= y|

## 4. 논리 연산자(Logical operators)
논리 연산자는 조건문을 결합하는 데 사용됩니다.
|Operator|	Description|	Example|
|--------|-------------|-----------|
|and| 	둘 다 True이면 True|	x < 5 and  x < 10	
|or|	둘중 하나가 True이면 True|	x < 5 or x < 4	
|not|	반대의 결과, 결과가 True이면 False |	not(x < 5 and x < 10)

## 5. Membership operators
|Operator|	Description|	Example|
|--------|-------------|-----------|
|in| 	Returns True if a sequence with the specified value is present in the object|	x in y|	
|not in|	Returns True if a sequence with the specified value is not present in the object|	x not in y|

# Exercises
[py-exercises-6](https://wontaejang.github.io/2021/07/04/py-exercises-6/)

# Reference
[w3schools python](https://www.w3schools.com/python)