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

# 7. 렉시컬 스코프 

``` javascript
var x = 1;

function foo() {
  var x = 10;
  bar();
}

function bar() {
  console.log(x);
}

foo(); // ?
bar(); // ?
```

위 예제의 실행 결과는 함수 bar의 상위 스코프가 무엇인지에 따라 결정된다. 두가지 패턴을 예측할 수 있는데 첫번째는 함수를 어디서 호출하였는지에 따라 상위 스코프를 결정하는 것이고 두번째는 함수를 어디서 선언하였는지에 따라 상위 스코프를 결정하는 것이다. 첫번째 방식으로 함수의 상위 스코프를 결정한다면 함수 bar의 상위 스코프는 함수 foo와 전역일 것이고, 두번째 방식으로 함수의 스코프를 결정한다면 함수 bar의 스코프는 전역일 것이다.

프로그래밍 언어는 이 두가지 방식 중 하나의 방식으로 함수의 상위 스코프를 결정한다. 첫번째 방식을 동적 스코프(Dynamic scope)라 하고, 두번째 방식을 렉시컬 스코프(Lexical scope) 또는 정적 스코프(Static scope)라 한다. 자바스크립트를 비롯한 대부분의 프로그래밍 언어는 렉시컬 스코프를 따른다.

**렉시컬 스코프는 함수를 어디서 호출하는지가 아니라 어디에 선언하였는지에 따라 결정된다. ** 자바스크립트는 렉시컬 스코프를 따르므로 함수를 선언한 시점에 상위 스코프가 결정된다. 함수를 어디에서 호출하였는지는 스코프 결정에 아무런 의미를 주지 않는다. 위 예제의 함수 bar는 전역에 선언되었다. 따라서 함수 bar의 상위 스코프는 전역 스코프이고 위 예제는 전역 변수 x의 값 1을 두번 출력한다.

# 8. 암묵적 전역
``` javascript
var x = 10; // 전역 변수

function foo () {
  // 선언하지 않은 식별자
  y = 20;
  console.log(x + y);
}

foo(); // 30
```

위 예제의 y는 선언하지 않은 식별자이다. 따라서 y = 20이 실행되면 참조 에러가 발생할 것처럼 보인다. 하지만 선언하지 않은 식별자 y는 마치 선언된 변수처럼 동작한다. 이는 선언하지 않은 식별자에 값을 할당하면 전역 객체의 프로퍼티가 되기 때문이다.

foo 함수가 호출되면 자바스크립트 엔진은 변수 y에 값을 할당하기 위해 먼저 스코프 체인을 통해 선언된 변수인지 확인한다. 이때 foo 함수의 스코프와 전역 스코프 어디에서도 변수 y의 선언을 찾을 수 없으므로 참조 에러가 발생해야 하지만 자바스크립트 엔진은 y = 20을 window.y = 20으로 해석하여 프로퍼티를 동적 생성한다. 결국 y는 전역 객체의 프로퍼티가 되어 마치 전역 변수처럼 동작한다. 이러한 현상을 암묵적 전역(implicit global)이라 한다.

하지만 y는 변수 선언없이 단지 전역 객체의 프로퍼티로 추가되었을 뿐이다. 따라서 y는 변수가 아니다. 따라서 변수가 아닌 y는 변수 호이스팅이 발생하지 않는다.

``` javascript
// 전역 변수 x는 호이스팅이 발생한다.
console.log(x); // undefined
// 전역 변수가 아니라 단지 전역 프로퍼티인 y는 호이스팅이 발생하지 않는다.
console.log(y); // ReferenceError: y is not defined

var x = 10; // 전역 변수

function foo () {
  // 선언하지 않은 변수
  y = 20;
  console.log(x + y);
}

foo(); // 30
```

또한 변수가 아니라 단지 프로퍼티인 y는 delete 연산자로 삭제할 수 있다. 전역 변수는 프로퍼티이지만 delete 연산자로 삭제할 수 없다.

``` javascript
var x = 10; // 전역 변수

function foo () {
  // 선언하지 않은 변수
  y = 20;
  console.log(x + y);
}

foo(); // 30

console.log(window.x); // 10
console.log(window.y); // 20

delete x; // 전역 변수는 삭제되지 않는다.
delete y; // 프로퍼티는 삭제된다.

console.log(window.x); // 10
console.log(window.y); // undefined
```

# 9. 최소한의 전역변수 사용
전역변수 사용을 최소화하는 방법 중 하나는 애플리케이션에서 전역변수 사용을 위해 다음과 같이 전역변수 객체 하나를 만들어 사용하는 것이다. (더글라스 크락포드의 제안)
``` javascript
var MYAPP = {};

MYAPP.student = {
  name: 'Lee',
  gender: 'male'
};

console.log(MYAPP.student.name);
```

# 10. 즉시실행함수를 이용한 전역변수 사용 억제
전역변수 사용을 억제하기 위해, 즉시 실행 함수(IIFE, Immediately-Invoked Function Expression)를 사용할 수 있다. 이 방법을 사용하면 전역변수를 만들지 않으므로 라이브러리 등에 자주 사용된다. 즉시 실행 함수는 즉시 실행되고 그 후 전역에서 바로 사라진다.

``` javascript
(function () {
  var MYAPP = {};

  MYAPP.student = {
    name: 'Lee',
    gender: 'male'
  };

  console.log(MYAPP.student.name);
}());

console.log(MYAPP.student.name);
```

# Reference
[poiemaweb.com/js-scope](https://poiemaweb.com/js-scope)