---
title: js-day5-control-flow
date: 2021-06-21 16:51:42
    - javascript 
    - ControlFlow
categories: 
    - javascript
---

### Control Flow
## 제어문

제어문(Control flow statement)은 주어진 조건에 따라 코드 블록을 실행(조건문)하거나 반복 실행(반복문)할 때 사용한다. 

일반벅으로 코드는 위에서 아래 방향으로 순차적으로 실행된다. 제어문은 코드의 실행 순서를 인위적으로 제어할 수 있다.

# 1.블록문
블록문(Block statement/Compound statement)는 0개 이상의 문들을 중괄호로 묶은 것으로 코드 블록 또는 블록이라고 부르기도 한다. 자바스크립트는 블록문을 하나의 단위로 취급한다. 

블록문은 단독으로 사용할 수도 있으나 일반적으로 제어문이나 함수 선언문 등에서 사용한다. 문의 끝에는 세미 콜론(;)을 붙이는 것이 일반적이지만 블록문은 세미 콜론을 붙이지 않는다. 

``` javascript
// 블록문
{
  var foo = 10;
  console.log(foo);
}

// 제어문
var x = 0;
while (x < 10) {
  x++;
}
console.log(x); // 10

// 함수 선언문
function sum(x, y) {
  return x + y;
}
console.log(sum(1, 2)); // 3
```

# 2.조건문
조건문(conditional statement)은 주어진 조건식(conditional expression)의 평가 결과에 따라 코드 블록(블록문)의 실행을 결정한다. 조건식은 불리언 값으로 평가될 수 있는 표현식이다.

자바스크립트는 2가지의 조건문 if...else 문과 switch 문을 제공한다.

## 2.1 if...else 문
if...else 문은 주어진 조건식(불리언 값으로 평가될 수 있는 표현식)의 평가 결과, 즉 논리적 참, 거짓에 따라 실행할 코드 블록을 결정한다. 만약 조건식의 평가 결과가 불리언 값이 아니면 불리언 값으로 강제변환되어 논리적 참, 거짓을 구별한다.

``` javascript
if (조건식) {
  // 조건식이 참이면 이 코드 블록이 실행된다.
} else {
  // 조건식이 거짓이면 이 코드 블록이 실행된다.
}
```

조건식의 평가 결과가 참(true)일 경우, if문 다음의 코드 블록이 실행된다. 거짓(false)일 경우, else 문 다음의 코드 블록이 실행된다. 

조건식을 추가하고 싶으면 else if 문을 사용한다.

``` javascript
if (조건식1) {
  // 조건식1이 참이면 이 코드 블록이 실행된다.
} else if (조건식2) {
  // 조건식2이 참이면 이 코드 블록이 실행된다.
} else {
  // 조건식1과 조건식2가 모두 거짓이면 이 코드 블록이 실행된다.
}
```

else if 문과 else 문은 옵션으로 사용할 수도 있고 사용하지 않을 수도 있다. if문과 else 문은 2번 이상 사용할 수 없지만 else if문은 여러번 사용할 수도 있다.

``` javacript
var num = 2;
var kind;

// if 문
if (num > 0) {
  kind = '양수'; // 음수를 구별할 수 없다
}
console.log(kind); // 양수

// if…else 문
if (num > 0) {
  kind = '양수';
} else {
  kind = '음수'; // 0은 음수가 아니다
}
console.log(kind); // 양수

// if…else if 문
if (num > 0) {
  kind = '양수';
} else if (num < 0) {
  kind = '음수';
} else {
  kind = '영';
}
console.log(kind); // 양수
```

만약 코드 블록 내의 문이 하나뿐이라면 중괄호를 생략할 수 있다.

``` javascript
var num = 2;
var kind;

if (num > 0)      kind = '양수';
else if (num < 0) kind = '음수';
else              kind = '영';

console.log(kind); // 양수
```

대부분의 if...else 문은 연산자에서 살펴본 삼항 조건 연산자로 바꿔쓸 수 있다. 아래 예제를 살펴보자.

``` javascript
// x가 짝수이면 ‘짝수'를 홀수이면 ‘홀수'를 반환한다.
var x = 2;
var result;

if (x % 2) { // 2 % 2는 0이고 0은 false로 취급된다.
  result = '홀수';
} else {
  result = '짝수';
}

console.log(result); // 짝수
```

위 예제는 아래와 같이 삼항 조건 연산자로 바꿔쓸 수 있다. 

``` javascript
// x가 짝수이면 '짝수'를 홀수이면 '홀수'를 반환한다.
var x = 2;

// 0은 false로 취급된다.
var result = x % 2 ? '홀수' : '짝수';
console.log(result); // 짝수
```

위 예제는 두가지 경우의 수 ('홀수' 또는 '짝수')를 갖는 경우이다. 만약 세가지 경우의 수는 아래와 같이 바꿔쓸 수 있다. 

``` javascript
var num = 2;

// 0은 false로 취급된다.
var kind = num ? (num > 0 ? '양수' : '음수') : '영';
console.log(kind); // 양수
```

num > 0? '양수' : '음수' 는 표현식이므로 다른 표현식의 일부가 될 수 있다.

## 2.2 switch 문
switch 문은 switch 문의 표현식을 평가하여 그 값과 일치하는 표현식을 갖는 case 문으로 실행 순서를 이동시킨다. 

case 문은 상황(case)을 의미하는 표현식을 지정하고 콜론으로 마친다. 그리고 그 뒤에 실행할 문들을 위치시킨다. 

switch 문의 표현식과 일치하는 표현식을 갖는 case 문이 없다면 실행 순서는 default 문으로 이동한다. default 옵션으로 사용할 수도 있고 사용하지 않을 수도 있다. 

``` code
switch (표현식) {
  case 표현식1:
    switch 문의 표현식과 표현식1이 일치하면 실행될 문;
    break;
  case 표현식2:
    switch 문의 표현식과 표현식2가 일치하면 실행될 문;
    break;
  default:
    switch 문의 표현식과 일치하는 표현식을 갖는 case 문이 없을 때 실행될 문;
}
```

if...else 문의 조건식은 반드시 불리언 값으로 평가되지만 switch 문의 표현식은 불리언 값보다는 문자열, 숫자 값인 경우가 많다. if...else 문은 논리적 참, 거짓으로 실행할 코드 블록을 결정한다. switch 문은 논리적 참, 거짓보다는 다양한 상황(case)에 따라 실행할 코드 블록을 결정할 때 사용한다. 

아래 예제를 살펴보자. switch 문의 표현식, 즉 변수 month의 평가 결과인 숫자 값 11과 일치하는 case 문으로 실행 순서가 이동한다. 

``` javascript
// 월을 영어로 변환한다. (11 → 'November')
var month = 11;
var monthName;

switch (month) {
  case 1:
    monthName = 'January';
  case 2:
    monthName = 'February';
  case 3:
    monthName = 'March';
  case 4:
    monthName = 'April';
  case 5:
    monthName = 'May';
  case 6:
    monthName = 'June';
  case 7:
    monthName = 'July';
  case 8:
    monthName = 'August';
  case 9:
    monthName = 'September';
  case 10:
    monthName = 'October';
  case 11:
    monthName = 'November';
  case 12:
    monthName = 'December';
  default:
    monthName = 'Invalid month';
}

console.log(monthName); // Invalid month
```

그런데 위 예제를 실행해 보면 ‘November’가 출력되지 않고 ‘Invalid month’가 출력된다. 이는 switch 문의 표현식의 평가 결과와 일치하는 case 문으로 실행 순서가 이동하여 문을 실행한 것은 맞지만, 문을 실행한 후 switch 문을 탈출하지 않고 switch 문이 끝날 때까지 모든 case 문과 default 문을 실행했기 때문이다. 이를 폴스루(fall through)라 한다. 다시 말해 변수 monthName에 ‘November’가 할당된 후 switch 문을 탈출하지 않고 연이어 ‘December’가 재할당되고 마지막으로 ‘Invalid month’가 재할당되었다.

결과가 이러한 이유는 case 문에 해당하는 문의 마지막에 break 문을 사용하지 않았기 때문이다. break 키워드로 구성된 break 문은 코드 블록에서 탈출하는 역할을 수행한다. break 문이 없다면 case 문의 표현식과 일치하지 않더라도 실행 순서는 다음 case 문으로 연이어 이동한다. 올바른 switch 문은 아래와 같다.

``` javascript
// 월을 영어로 변환한다. (11 → 'November')
var month = 11;
var monthName;

switch (month) {
  case 1:
    monthName = 'January';
    break;
  case 2:
    monthName = 'February';
    break;
  case 3:
    monthName = 'March';
    break;
  case 4:
    monthName = 'April';
    break;
  case 5:
    monthName = 'May';
    break;
  case 6:
    monthName = 'June';
    break;
  case 7:
    monthName = 'July';
    break;
  case 8:
    monthName = 'August';
    break;
  case 9:
    monthName = 'September';
    break;
  case 10:
    monthName = 'October';
    break;
  case 11:
    monthName = 'November';
    break;
  case 12:
    monthName = 'December';
    break;
  default:
    monthName = 'Invalid month';
}

console.log(monthName); // November
```

default 문에는 break 문을 생략하는 것이 일반적이다. default 문은 switch 문의 가장 마지막에 위치하므로 default 문의 실행이 종료하면 switch 문을 빠져나간다. 따라서 별도로 break 문이 필요없다.

case 문은 반드시 단독으로 사용되어야 하는 것은 아니다. 아래 예제와 같이 여러 개의 case 문을 중복해 사용할 수도 있다. 아래는 윤년인지 판별해서 2월의 일수를 계산하는 예제다.

``` javascript
var year = 2000; // 2000년은 윤년으로 2월이 29일이다.
var month = 2;
var days = 0;

switch (month) {
  case 1: case 3: case 5: case 7: case 8: case 10: case 12:
    days = 31;
    break;
  case 4: case 6: case 9: case 11:
    days = 30;
    break;
  case 2:
    // 윤년 계산 알고리즘
    // 1. 년도가 4로 나누어 떨어지는 해는 윤년(2000, 2004, 2008, 2012, 2016, 2020…)
    // 2. 그 중에서 년도가 100으로 나누어 떨어지는 해는 평년(2000, 2100, 2200...)
    // 3. 그 중에서 년도가 400으로 나누어 떨어지는 해는 윤년(2000, 2400, 2800...)
    days = ((year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0)) ? 29 : 28;
    break;
  default:
    console.log('Invalid month');
}

console.log(days); // 29
```

switch 문은 case, default, break 등 다양한 키워드를 사용해야 하고 폴스루가 발생하는 등 문법도 복잡하다. if…else 문으로 해결할 수 있다면 if…else 문을 사용하는 편이 좋다. 하지만 if…else 문보다 switch 문을 사용했을 때 가독성이 더 좋다면 switch 문을 사용하는 편이 좋다.

# 3. 반복문
반복문(Loop statement)은 주어진 조건식(conditional expression)의 평가 결과가 참인 경우 코드 블록을 실행한다. 그 후 조건식을 다시 검사하여 여전히 참인 경우 코드 블록을 다시 실행한다. 이는 조건식이 거짓일 때까지 반복된다. 

자바스크립트는 3가지 반복문 for문, while문, do...while문을 제공한다. 그 외에도 for...in문, ES6에서 새롭게 도입된 for...of문이 있다. for...in 문과 for...of문에 대해서는 나중에 살펴보기로 하자.

