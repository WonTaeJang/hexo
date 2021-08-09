---
title: js-day12-scope
date: 2021-08-09 09:57:47
    - javascript 
    - scope
categories: 
    - javascript
---

# 1. 스코프란? 
스코프(Scope, 유효범위)는 자바스크립트를 포함한 모든 프로그래밍 언어의 기본적인 개념으로 확실한 이해가 필요하다. 먼저 아래 예제의 실행 결과에 대해 생각해보자. 

``` javascript
var x = 'global';

function foo () {
  var x = 'function scope';
  console.log(x);
}

foo(); // ?
console.log(x); // ?
```

이름이 같은 변수 x가 중복 선언되었다. 전역에서 변수 x를 참조할 때, 그리고 함수 foo 내부에서 변수 x를 참조할 때 이름이 중복된 2개의 변수 중 어떤 변수를 참조해야 하는가? 자바스크립트는 어떻게 변수를 식별하는 것일까?

**스코프는 참조 대상 식별자(identifier, 변수, 함수의 이름과 같이 어떤 대상을 다른 대상과 구분하여 식별할 수 있는 유일한 이름)를 찾아내기 위한 규칙이다. 자바스크립트는 이 규칙대로 식별자를 찾는다.**

프로그래밍은 변수를 선언하고 값을 할당하며 변수를 참조하는 기본적인 기능을 제공하며 이것으로 프로그램의 상태를 관리할 수 있다. 변수는 전역 또는 코드 블록(if, for, while, try/catch 등)이나 함수 내에 선언하며 코드 블록이나 함수는 중첩될 수 있다. 식별자는 자신이 어디에서 선언됐는지에 의해 자신이 유효한(다른 코드가 자신을 참조할 수 있는) 범위를 갖는다.

위 예제에서 전역에 선언된 변수 x는 어디에든 참조할 수 있다. 하지만 함수 foo 내에서 선언된 변수 x는 함수 foo 내부에서만 참조할 수 있고 함수 외부에서는 참조할 수 없다. 이러한 규칙을 스코프라고 한다.

# 2. 스코프의 구분
자바스크립트에서 스코프를 구분해보면 다음과 같이 2가지로 나눌 수 있다. 

> **전역 스코프(Global scope)**         
> 코드 어디에서든지 참조할 수 있다.

> **지역 스코프(Local scope or Function-level scope)**          
> 함수 코드 블록이 만든 스코프로 함수 자신과 하위 함수에서만 참조할 수 있다.

모든 변수는 스코프를 갖는다. 변수의 관점에서 스코프를 구분하면 다음과 같이 2가지로 나눌 수 있다.

> **전역변수(Global variable)**         
> 전역에서 선언된 변수이며 어디에든 참조할 수 있다.

> **지역변수(Local variable)**          
> 지역(함수)내에서 선언된 변수이며 그 지역과 그 지역의 하부 지역에서만 참조할 수 있다.

변수는 선언 위치(전역 또는 지역)에 의해 스코프를 가지게 된다. 즉, 전역에서 선언된 변수는 전역 스코프를 갖는 전역 변수이고, 지역(자바스크립트의 경우 함수 내부)에서 선언된 변수는 지역 스코프를 갖는 지역 변수가 된다. 

전역 스코프를 갖는 전역(코드 어디서든지)에서 참조할 수 있다. 지역(함수 내부)에서 선언된 지역 변수는 그 지역과 그 지역의 하부 지역에서만 참조할 수 있다. 


# 3. 자바스크립트 스코프의 특징
자바스크립트의 스코프는 타 언어와는 다른 특징을 가지고 있다. 

대부분의 C-family language는 블록 레벨 스코프(block-level scope)를 따른다. 블록 레벨 스코프란 코드 블록({…})내에서 유효한 스코프를 의미한다. 여기서 “유효하다”라는 것은 “참조(접근)할 수 있다”라는 뜻이다.

``` C++
int main(void) {
  // block-level scope
  if (1) {
    int x = 5;
    printf("x = %d\n", x);
  }

  printf("x = %d\n", x); // use of undeclared identifier 'x'

  return 0;
}
```

위의 C언어 코드를 보면 if문 내에서 선언된 변수 x는 if문 코드 블록 내에서만 유효하다. 즉, if문 코드 블록 밖에서는 참조가 불가능하다. 

하지만 자바스크립트는 **함수 레벨 스코프**를 따른다. 함수 레벨 스코프란 함수 코드 블록 내에서 선언된 변수는 함수 코드 블록 내에서만 유효하고 함수 외부에서는 유효하지 않다(참조할 수 없다)는 것이다.

단, ECMAScript 6에서 도입된 let keyword를 사용하면 **블록 레벨 스코프**를 사용할 수 있다.

``` javascript
var x = 0;
{
  var x = 1;
  console.log(x); // 1
}
console.log(x);   // 1

let y = 0;
{
  let y = 1;
  console.log(y); // 1
}
console.log(y);   // 0
```

# 4. 전역 스코프(Global scope)
전역에 변수를 선언하면 이 변수는 어디서든지 참조할 수 있는 전역 스코프를 갖는 전역 변수가 된다. var 키워드로 선언한 전역 변수는 전역 객체(Global Object) window의 프로퍼티이다. 

``` javascript
var global = 'global';

function foo() {
  var local = 'local';
  console.log(global);
  console.log(local);
}
foo();

console.log(global);
console.log(local); // Uncaught ReferenceError: local is not defined
```

변수 global는 함수 영역밖의 전역에서 선언되었다. 자바스크립트는 타 언어와는 달리 특별한 시작점(Entry point)이 없어서 위 코드와 같이 전역에 변수나 함수를 선언하기 쉽다. 

C언어의 경우 main 함수가 시작점이 되기 때문에 대부분은 코드는 main 함수 내에 포함된다. C언어의 경우 전역 변수를 선언하기 위해서는 의도적으로 main함수 밖에 변수를 선언하여야 한다.

``` c++
#include <stdio.h>

/* global variable declaration */
int g;

int main () {

  // local variable declaration
  int a, b;

  // actual initialization
  a = 10;
  b = 20;
  g = a + b;

  printf ("value of a = %d, b = %d and g = %d\n", a, b, g);

  return 0;
}
```

하지만 자바스크립트는 다른 C-family language와는 달리 특별한 시작점이 없으며 코드가 나타나는 즉시 해석되고 실행된다. 따라서 전역에 변수를 선언하기 쉬우며 이것는 전역 변수를 남발하게 하는 문제를 야기시킨다.

전역 변수의 사용은 변수 이름이 중복될 수 있고, **의도치 않은 재할당에 의한 상태 변화로 코드를 예측하기 어렵게 만드므로 사용을 억제하여야 한다.**

# 5. 비 블록 레벨 스코프(Non block-level scope)
``` javascript
if (true) {
  var x = 5;
}
console.log(x);
```

변수 x는 코드 블록 내에서 선언되었다. 하지만 자바스크립트는 블록 레벨 스코프를 사용하지 않으므로 **함수 밖에서 선언된 변수는 코드 블록 내에서 선언되었다 할지라도 모두 전역 스코프**를 갖게된다. 따라서 변수 x는 전역 변수이다. 

# 6. 함수 레벨 스코프(Function-level scope)
``` javascript
var a = 10;     // 전역변수

(function () {
  var b = 20;   // 지역변수
})();

console.log(a); // 10
console.log(b); // "b" is not defined
```

자바스크립트는 함수 레벨 스코프를 사용한다. 즉, 함수 내에서  선언된 매개변수와 변수는 함수 외부에서는 유효하지 않다. 따라서 변수 b는 지역변수이다. 

``` javascript
var x = 'global';

function foo() {
  var x = 'local';
  console.log(x);
}

foo();          // local
console.log(x); // global
```

전역변수 x와 지역변수 x가 중복 선언되었다. 전역 영역에서는 전역변수만이 참조 가능하고 함수 내 지역 영역에서는 전역과 지역 변수 모두 참조 가능하나 위 예제와 같이 변수명이 중복된 경우, 지역변수를 우선하여 참조한다.

다음은 함수 내에 존재하는 함수인 내부 함수의 경우를 살펴보자.

``` javascript
var x = 'global';

function foo() {
  var x = 'local';
  console.log(x);

  function bar() {  // 내부함수
    console.log(x); // ?
  }

  bar();
}
foo();
console.log(x); // ?
```

내부함수는 자신을 포함하고 있는 외부함수의 변수에 접근할 수 있다. 이는 매우 유용하다. 클로저에서와 같이 내부함수가 더 오래 생존하는 경우, 타 언어와는 다른 움직임을 보인다.

함수 bar에서 참조하는 변수 x는 함수 foo에서 선언된 지역변수이다. 이는 실행 컨텍스트의 스코프 체인에 의해 참조 순위에서 전역변수 x가 뒤로 밀렸기 때문이다.

``` javascript
var x = 10;

function foo() {
  x = 100;
  console.log(x);
}
foo();
console.log(x); // ?
```

함수(지역) 영역에서 전역변수를 참조할 수 있으므로 전역변수의 값도 변경할 수 있다. 내부 함수의 경우, 전역변수는 물론 상위 함수에서 선언한 변수에 접근/변경이 가능하다.

``` javascript
var x = 10;

function foo(){
  var x = 100;
  console.log(x);

  function bar(){   // 내부함수
    x = 1000;
    console.log(x); // ?
  }

  bar();
}
foo();
console.log(x); // ?
```

중첩 스코프는 가장 인접한 지역을 우선하여 참조한다.

``` javascript
var foo = function ( ) {

  var a = 3, b = 5;

  var bar = function ( ) {
    var b = 7, c = 11;

// 이 시점에서 a는 3, b는 7, c는 11

    a += b + c;

// 이 시점에서 a는 21, b는 7, c는 11

  };

// 이 시점에서 a는 3, b는 5, c는 not defined

  bar( );

// 이 시점에서 a는 21, b는 5

};
```