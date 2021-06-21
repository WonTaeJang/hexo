---
title: js-jay-control-flow
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