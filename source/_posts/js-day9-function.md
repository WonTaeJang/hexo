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