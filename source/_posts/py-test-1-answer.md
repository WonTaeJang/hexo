---
title: py-test-1-answer
date: 2021-07-11 22:14:10
    - python 
    - testanswer
categories: 
    - python-test
---

# TEST 1
while문을 이용하여 구구단을 출력하시오. 
> 출력 예시:        
> 구구단 1단: 1 X 1 = 1     
> 구구단 1단: 1 X 2 = 2     
> ...   
> 구구단 9단: 9 X 9 = 81  

TEST 1 Answer
``` python
i = 1
j = 1

while(i <= 9):
    j = 1
    while(j <= 9):
        print(str.format("구구단 {0}단: {1} X {2} = {3}", i, i, j, i*j))
        j += 1
        
    i+= 1
```


# TEST 2 
for문을 이용하여 구구단 짝수만 출력하시오. 
> 출력 예시:        
> 구구단 2단: 2 X 1 = 2     
> 구구단 2단: 2 X 2 = 4     
> ...   
> 구구단 8단: 8 X 9 = 72  

TEST 2 Answer
``` python
i = 1
j = 1

for x in range(1, 10):
    for y in range(1, 10):
        if (x % 2 == 0):
            print(str.format("구구단 {0}단: {1} X {2} = {3}", x, x, y, x*y))
```

# TEST 3
``` python
fruits = ["apple", "banana", "cherry", "pear", "chestnut", "grape", "melon", "lemon"," citron", "apricot"]

fruits_1 = ["apple", "chestnut", "grape", "melon", "lemon", "apricot"]

fruits_2 = ["banana", "grape", "cherry", "pear", "chestnut",  "lemon", "citron"]
```
## TEST 3.0
fruits에 "watermelon"을 추가하여 알파벳 순으로 출력하시오.

TEST 3.0 Answer
``` python
fruits.append("watermelon")
fruits.sort()
print(fruits)
```

## TEST 3.1
fruits_1 list와 fruits_2 list의 item을 비교하여 똑같은 item가 있을 경우 해당 item을 출력하시오.

TEST 3.1 Answer
``` python
for x in range(len(fruits_1)):
    for y in range(len(fruits_2)):
        if(fruits_1[x] == fruits_2[y]):
            print(fruits_2[y])
```

## TEST 3.2
fruits list의 과일을 하나씩 출력하는데 알파벳 "c"인 과일은 빼고 출력하시오.

TEST 3.2 Answer
``` python
for x in range(len(fruits)):
    y = fruits[x]

    if(y[0] != 'c'):
        print(fruits[x])
```

## TEST 3.3
fruits_1 과 fruits_2를 합쳐서 fruits_3를 만들어 출력하시오. 중복이 있을경우 한번만 들어가되 대문자로 넣으시오. 

TEST 3.3 Answer
``` python
# list 합치기
fruits_3 = fruits_1.copy()
fruits_3.extend(fruits_2)

# 겹치는 과일 deleteList에 넣기
deleteList = []
for x in range(len(fruits_3)):
    count = 0

    for y in range(len(fruits_3)):
        if(fruits_3[x] == fruits_3[y]):
            count += 1
        
        if(count == 2):
            if fruits_3[y] in deleteList:
                pass
            else:
                deleteList.append(fruits_3[y])

            break

# 겹치는 과일 1개 삭제
for x in range(len(deleteList)):
    fruits_3.remove(deleteList[x])

# 겹치는 과일 대문자로 변경
for x in range(len(deleteList)):
    for y in range(len(fruits_3)):
        if(fruits_3[y] == deleteList[x]):
            z = deleteList[x]
            fruits_3[y] = z.upper()

print(fruits_3)
```