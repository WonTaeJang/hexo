---
title: py-day13-while
date: 2021-07-06 10:46:47
   - python 
   - while
categories: 
   - python
---

# Python While Loops
Python에는 두가지 기본 Loop 명령이 있다.
- while loop
- for loop

## while loop
while문은 조건이 충족할때까지 해당 코드 블록이 무한번 반복한다.
> With the while loop we can execute a set of statements as long as a condition is true.

### example
``` python
i = 1
while i < 6:
  print(i)
  i += 1
```

## break 문
break 문은 loop를 빠져 나올수 있다.
> With the break statement we can stop the loop even if the while condition is true:

### example
``` python
i = 1
while i < 6:
  print(i)
  if i == 3:
    break
  i += 1
```

## continue문
continue문은 현재의 반복을 중지하고 다음 반복으로 넘어간다.
> With the continue statement we can stop the current iteration, and continue with the next

### example
``` python
i = 0
while i < 6:
  i += 1
  if i == 3:
    continue
  print(i)
```

## else 문
while문이 끝나고 else를 실행할 수 있다.
>With the else statement we can run a block of code once when the condition no longer is true

### example
``` python
i = 1
while i < 6:
  print(i)
  i += 1
else:
  print("i is no longer less than 6")
```
# Exercises
[py-exercises-9](https://wontaejang.github.io/2021/07/06/py-exercises-9/)

# Reference
[w3schools python](https://www.w3schools.com/python)