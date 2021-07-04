---
title: py-day11-list-2
date: 2021-07-04 14:01:19
   - python 
   - lists
categories: 
   - python
---

# List Items 접근 (Access List Items)

## 1. Items 접근 
### example
``` python
thislist = ["apple", "banana", "cherry"]
print(thislist[1])
```
> Note: 첫번째 item은 index 0이다.

## 2. Negative Indexing
-1 은 마지막 item을 나타내며 오른쪽 부터 -1, -2, -3... 순이다.

### example
``` python
thislist = ["apple", "banana", "cherry"]
print(thislist[-1])
```

## 3. Range of Indexes
list에 index 범위를 설정하여 해당 구역의 item만 list로 반환된다.

### example
``` python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[2:5])
```
> Note: index 2는 포함, index 5는 미포함

### example
``` python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[:4])
```

### example
``` python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[2:])
```

### example
``` python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[-4:-1])
```

## 4. Item이 있는지 확인
in 키워드를 사용하여 list에 해당 item이 있는지 확인 가능하다.

### example
``` python
thislist = ["apple", "banana", "cherry"]
if "apple" in thislist:
  print("Yes, 'apple' is in the fruits list")
```


# Reference
[w3schools python](https://www.w3schools.com/python)