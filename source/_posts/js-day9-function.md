---
title: js-day9-function
date: 2021-07-23 17:12:01
    - javascript 
    - function
categories: 
    - javascript
---

함수란 어떤 작업을 수행하기 위해 필요한 문(statement)들의 집합을 정의한 코드 블록이다. 함수는 이름과 매개변수를 갖으며 필요한 때에 호출하여 코드 블록에 담긴 문들을 일괄적으로 실행할 수 있다. 

``` javascript
// 함수의 정의(함수 선언문)
function square(number) {
  return number * number;
}
```

함수는 호출에 의해 실행되는데 한번만 호출할 수 있는 것이 아니라 여러번 호출할 수 있다. 

``` javascript
// 함수의 정의(함수 선언문)
function square(number) {
  return number * number;
}

// 함수의 호출
square(2); // 4
```

동일한 작업을 반복적으로 수행해야 한다면 (동일한 구문을 계속해서 중복해서 작성하는 것이 아니라) 미리 정의된 함수를 재사용하는 것이 효율적이다. 이러한 특성은 코드의 재사용이라는 측면에서 매우 유용하다.

함수의 일반적 기능은 어떤 작업을 수행하는 문(statement)들의 집합을 정의하여 코드의 재사용에 목적이 있다. 이러한 일반적 기능 이외에 객체 생성, 객체의 행위 정의(메소드), 정보 은닉, 클로저, 모듈화 등의 기능을 수행할 수 있다.

자바스크립트의 함수는 객체(일급 객체, First-class object)이다. 다른 객체와 구분될 수 있는 특징은 호출할 수 있다는 것이다. 함수도 객체이므로 다른 값들처럼 사용할 수 있다. 즉, 변수나 객체, 배열 등에 저장할 수 있고 다른 함수에 전달되는 인수로도 사용할 수 있으며 함수의 반환값이 될 수도 있다.

# 1. 함수 정의 
함수를 정의하는 방식은 3가지가 있다. 

- 함수 선언문
- 함수 표현식
- Function 생성자 함수

## 1.1 함수 선언문 
함수 선언문(Function declaration) 방식으로 정의한 함수는 function 키워드와 이하의 내용으로 구성된다. 

> - 함수명  
> 함수 선언문의 경우, 함수명은 생략할 수 없다. 함수명은 함수 몸체에서 자신을 재귀적(recursive)호출하거나 자바스크립트 디버거가 해당 함수를 구분할 수 있는 식별자이다. 

> - 매개변수 목록
> 0개 이상의 목록으로 괄호로 감싸고 콤마로 분리한다. 다른 언어와의 차이점은 매개변수의 타입을 기술하지 않는다는 것이다. 이 때문에 함수 몸체 내에서 매개변수의 타입 체크가 필요할 수 있다. 

> - 함수 몸체
> 함수가 호출되었을 때 실행되는 문들의 집합이다. 중괄호({})로 문들을 감싸고 return 문으로 결과값을 반환할 수 있다. 이를 반환값 (return value)라 한다. 

``` javascript
// 함수 선언문
function square(number) {
  return number * number;
}
```

## 1.2 함수 표현식 
자바스크립트의 함수는 [일급 객체(first-class object)](https://ko.wikipedia.org/wiki/%EC%9D%BC%EA%B8%89_%EA%B0%9D%EC%B2%B4)이므로 아래와 같은 특징이 있다. 

> 1. 무명의 리터럴로 표현이 가능하다. 
> 2. 변수나 자료 구조(객체, 배열... )에 저장할 수 있다. 
> 3. 함수의 파라미터로 전달할 수 있다. 
> 4. 반환값(return value)으로 사용할  수 있다. 

함수의 일급객체 특성을 이용하여 함수 리터럴 방식으로 함수를 정의하고 변수에 할당할 수 있는데 이러한 방식을 함수 표현식(Function expression)이라 한다. 

함수 선언문으로 정의한 함수 square()를 함수 표현식으로 정의하면 아래와 같다. 

``` javascript
// 함수 표현식
var square = function(number) {
  return number * number;
};
```

함수 표현식 방식으로 정의한 함수를 함수명을 생략할 수 있다. 이러한 함수를 익명 함수(anonymous function)이라 한다. 함수 표현식에서는 함수명을 생략하는 것이 일반적이다. 

``` javascript
// 기명 함수 표현식(named function expression)
var foo = function multiply(a, b) {
  return a * b;
};

// 익명 함수 표현식(anonymous function expression)
var bar = function(a, b) {
  return a * b;
};

console.log(foo(10, 5)); // 50
console.log(multiply(10, 5)); // Uncaught ReferenceError: multiply is not defined
```

함수는 일급객체이기 때문에 변수에 할당할 수 있는데 이 변수는 함수명이 아니라 할당된 함수를 가리키는 참조값을 저장하게 된다. 함수 호출 시 함수명이 아니라 함수를 가리키는 변수명을 사용하여야 한다. 

``` javascript
var foo = function(a, b) {
  return a * b;
};

var bar = foo;

console.log(foo(10, 10)); // 100
console.log(bar(10, 10)); // 100
```

변수 bar와 변수 foo는 동일한 익명 함수의 참조값을 갖는다. 

foo -> 익명 함수 <- bar

함수가 할당된 변수를 사용해 함수를 호출하지 않고 기명함수의 함수명을 사용해 호출하게 되면 에러가 발생한다. 이를 함수 표현식에서 사용한 함수명은 외부 코드에서 접근 불가능하기 때문이다. (사실 함수 선언문의 경우도 마찬가지이다.)

함수 표현식과 함수 선언문에서 사용한 함수명은 함수 몸체에서 자신을 재귀적 호출(Recursize function call)하거나 자바스크립트 디버거가 해당 함수를 구분할 수 있는 식별자의 역할을 한다. 

함수 선언문으로 정의한 함수 square의 경우, 함수명으로 호출 할 수 있었는데 이는 자바스크립트 엔진에 의해 아래와 같은 함수 표현식으로 형태가 변경되었기 때문이다. 

``` javascript
var square = function square(number) {
  return number * number;
};
```

함수명과 함수 참조값을 가진 변수명이 일치하므로 함수명으로 호출되는 듯 보이지만 사실은 변수명으로 호출된 것이다.

결국 함수 선언문도 함수 표현식과 동일하게 함수 리터럴 방식으로 정의되는 것이다.

## 1.3 Function 생성자 함수
함수 표현식으로 함수를 정의할 때 함수 리터럴 방식을 사용한다. 함수 선언문도 내부적으로 자바스크립트 엔진이 기명 함수 표현식으로 변환하므로 결국 함수 리터럴 방식을 사용한다. 

따라서 함수 선언문과 함수 표현식은 모두 함수 리터럴 방식으로 함수를 정의하는데 이것은 결국 내장 함수 Function 생성자 함수로 함수를 생성하는 것을 단순화 시킨 short-hand(축약법)이다. 

Function 생성자 함수는 Function.prototype.constructor 프로퍼티로 접근할 수 있다. 

Function 생성자 함수로 함수를 생성하는 문법은 다음과 같다. 

``` javascript
new Function(arg1, arg2, ... argN, functionBody)
```

``` javascript
var square = new Function('number', 'return number * number');
console.log(square(10)); // 100
```

Function 생성자 함수로 함수를 생성하는 방식은 일반적으로 사용하지 않는다. 

# 2. 함수 호이스팅
3가지의 함수 정의 방식을 알아보았다. 정의 방식은 달라도 결국 Function 생성자 함수를 통해 함수를 생성하는 것까지 확인하였다. 그런데 이 3가지 함수 정의 방식은 동작 방식에 약간의 차이가 있다. 

``` javascript
var res = square(5);

function square(number) {
  return number * number;
}
```

위 코드를 보면 함수 선언문으로 함수가 정의되기 이전에 함수 호출이 가능하다. 함수 선언문의 경우, 함수 선언의 위치와는 상관없이 코드 내 어느곳에서든지 호출이 가능한데 이것을 함수 호이스팅(Function Hoisting)이라 한다. 

자바스크립트는 ES6의 let, const를 포함하여 모든 선언(var, let, const, function, function*, class)을 호이스팅(Hoisting)한다. 

호이스팅이란 var 선언문이나 function 선언문 등 모든 선언문이 해당 Scope의 선두로 옮겨진 것처럼 동작하는 특성을 말한다. 즉, 자바스크립트는 모든 선언문(var, let, const, function, function*, class)이 선언되기 이전에 참조 가능하다. 

함수 선언문으로 정의된 함수는 자바스크립트 엔진이 스크립트가 로딩되는 시점에 바로 초기화하고 이를 vo(variable object)에 저장한다. 함수 선언, 초기화, 할당이 한번에 이루어진다. 그렇기 때문에 함수 선언의 위치와는 상관없이 소스 내 어느 곳에서든지 호출이 가능하다. 

다음은 함수 표현식으로 함수를 정의한 경우이다. 

``` javascript
var res = square(5); // TypeError: square is not a function

var square = function(number) {
  return number * number;
}
```

함수 선언문의 경우와는 달리 Type Error가 방생하였다. 함수 표현식의 경우 함수 호이스팅이 아니라 변수 호이스팅이 발생한다. 

> 변수 호이스팅은 생성 및 초기화와 할당이 분리되어 진행된다. 호이스팅된 변수는 undefined로 초기화 되고 실제값의 할당은 할당문에서 이루어 진다. 

함수 표현식은 함수 선언문과는 달리 스크립트 로딩 시점에 변수 객체(VO)에 함수를 할당하지 않고 runtime에 해석되고 실행되므로 이 두가지를 구분하는 것은 중요하다.

JavaScript: The Good Parts의 저자이며 자바스크립트의 권위자인 더글러스 크락포드(Douglas Crockford)는 이와 같은 문제 때문에 함수 표현식만을 사용할 것을 권고하고 있다. 함수 호이스팅이 함수 호출 전 반드시 함수를 선언하여야 한다는 규칙을 무시하므로 코드의 구조를 엉성하게 만들 수 있다고 지적한다.

또한 함수 선언문으로 함수를 정의하면 사용하기에 쉽지만 대규모 애플리케이션을 개발하는 경우 인터프리터가 너무 많은 코드를 변수 객체(VO)에 저장하므로 애플리케이션의 응답속도는 현저히 떨어질 수 있으므로 주의해야 할 필요가 있다.

# 3. First-class object(일급 객체)
일급 객체(first-class object)란 생성, 대입, 연산, 인자 또는 반환값으로서의 전달 등 프로그래밍 언어의 기본적 조작을 제한없이 사용할 수 있는 대상을 의미한다. 

다음 조건을 만족하면 일급 객체로 간주한다. 
> 1. 무명의 리터럴로 표현이 가능하다. 
> 2. 변수나 자료 구조(객체, 배열 등)에 저장할 수 있다. 
> 3. 함수의 매개변수에 전달할 수 있다. 
> 4. 반환값으로 사용할 수 있다. 

``` javascript
// 1. 무명의 리터럴로 표현이 가능하다.
// 2. 변수나 자료 구조에 저장할 수 있다.
var increase = function (num) {
  return ++num;
};

var decrease = function (num) {
  return --num;
};

var predicates = { increase, decrease };

// 3. 함수의 매개변수에 전달할 수 있다.
// 4. 반환값으로 사용할 수 있다.
function makeCounter(predicate) {
  var num = 0;

  return function () {
    num = predicate(num);
    return num;
  };
}

var increaser = makeCounter(predicates.increase);
console.log(increaser()); // 1
console.log(increaser()); // 2

var decreaser = makeCounter(predicates.decrease);
console.log(decreaser()); // -1
console.log(decreaser()); // -2
```

Javascript의 함수는 위의 조건을 모두 만족하므로 Javascript의 함수는 일급객체이다. 따라서 Javascript의 함수는 흡사 변수와 같이 사용할 수 있으며 코드의 어디에서든지 정의할 수 있다. 

**함수와 다른 객체를 구분짓는 특징은 호출할 수 있다는 것이다.**       


# 4. 매개변수(Parameter, 인자)
함수의 작업 실행을 위해 추가적인 정보가 필요할 경우, 매개변수를 지정한다. 매개변수는 함수 내에서 변수와 동일하게 동작한다.

## 4.1 매개변수(parameter, 인자) vs 인수(argument)
매개변수는 함수 내에서 변수와 동일하게 메모리 공간을 확보하며 함수에 전달한 인수는 매개변수에 할당된다. 만약 인수를 전달하지 않으면 매개변수는 Undefined로 초기화 된다. 

``` javascript
var foo = function (p1, p2) {
  console.log(p1, p2);
};

foo(1); // 1 undefined
```

## 4.2 Call-by-value
원시 타입 인수는 Call-by-value(값에 의한 호출)로 동작한다. 이는 함수 호출 시 원시 타입 인수를 함수에 매개변수로 전달할 때 매개변수에 값을 복사하여 함수로 전달하는 방식이다. 이때 함수 내에서 매개변수를 통해 값이 변경되어도 전달이 완료된 원시 타입 값은 변경되지 않는다.

``` javascript
function foo(primitive) {
  primitive += 1;
  return primitive;
}

var x = 0;

console.log(foo(x)); // 1
console.log(x);      // 0
```

## 4.3 Call-by-reference
객체형(참조형) 인수는 Call-by-reference(참조에 의한 호출)로 동작한다. 이는 함수 호출 시 참조 타입 인수를 함수에 매개변수로 전달할 때 매개변수에 값이 복사되지 않고 객체의 참조값이 매개변수에 저장되어 함수로 전달되는 방식이다. 이때 함수 내에서 매개변수의 참조값이 이용하여 객체의 값을 변경했을 때 전달되어진 참조형의 인수값도 같이 변경된다.

``` javascript
function changeVal(primitive, obj) {
  primitive += 100;
  obj.name = 'Kim';
  obj.gender = 'female';
}

var num = 100;
var obj = {
  name: 'Lee',
  gender: 'male'
};

console.log(num); // 100
console.log(obj); // Object {name: 'Lee', gender: 'male'}

changeVal(num, obj);

console.log(num); // 100
console.log(obj); // Object {name: 'Kim', gender: 'female'}
```

changeVal 함수는 원시 타입과 객체 타입 인수를 전달 받아 함수 몸체에서 매개변수의 값을 변경하였다. 이때 원시 타입 인수는 값을 복사하여 매개변수에 전달하기 때문에 함수 몸체에서 그 값을 변경하여도 어떠한 부수 효과(side-effect)도 발생시키지 않는다.

하지만 객체형 인수는 참조값을 매개변수에 전달하기 때문에 함수 몸체에서 그 값을 변경할 경우 원본 객체가 변경되는 부수 효과(side-effect)가 발생한다. 이와 같이 부수 효과를 발생시키는 비순수 함수(Impure function)는 복잡성을 증가시킨다. 비순수 함수를 최대한 줄이는 것은 부수 효과를 최대한 억제하는 것과 같다. 이것은 디버깅을 쉽게 만든다.

어떤 외부 상태도 변경하지 않는 함수를 순수함수(Pure function), 외부 상태도 변경시켜는 부수 효과(side-effect)가 발생시키는 함수를 비순수 함수(Impure function)라 한다.