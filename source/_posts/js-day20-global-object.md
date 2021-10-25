---
title: js-day20-global-object
date: 2021-10-25 22:58:38
    - javascript 
    - global-object
categories: 
    - javascript
---

# Global Object
전역 객체(Global Object)는 모든 객체의 유일한 최상위 객체를 의미하며 일반적으로 Browser-side에서는 window, Server-side( Node.js)에서는 global 객체를 의미한다. 

``` javascript
// in browser console
this === window // true

// in Terminal
node
this === global // true
```

- 전역 객체는 실행 컨텍스트에 컨트롤이 들어가기 이전에 생성이 되며 contructor가 없기 때문에 new 연산자를 이용하여 새롭게 생성할 수 없다. 즉, 개발자가 전역 객체를 생성하는 것은 불가능하다. 

- 전역 객체는 전역 스코프(Global Scope)를 갖게 된다. 

- 전역 객체의 자식 객체를 사용할 때 전역 객체의 기술은 생략할 수 있다. 예를 들어 document 객체는 전역 객체 window의 자식 객체로서 window.document... 와 같이 기술할 수 있으나 일반적으로 전역 객체의 기술은 생략한다. 

``` javascript
document.getElementById('foo').style.display = 'none';
// window.document.getElementById('foo').style.display = 'none';
```

- 그러나 사용자가 정의한 변수와 전역 객체의 자식 객체 이름이 충돌하는 경우, 명확히 전역 객체를 기술하여 혼동을 방지할 수 있다. 

``` javascript
function moveTo(url) {
  var location = {'href':'move to '};
  alert(location.href + url);
  // location.href = url;
  window.location.href = url;
}
moveTo('http://www.google.com');
```

- 전역 객체는 전역변수(Global variable)를 프로퍼티로 가지게 된다. 다시 말해 전역 변수는 전역 객체의 프로퍼티이다. 

``` javascript
var ga = 'Global variable';
console.log(ga);
console.log(window.ga);
```

- 글로벌 영역에 선언한 함수도 전역 객체의 프로퍼티로 접근할 수 있다. 다시 말해 전역 함수는 전역 객체의 메소드이다. 

``` javascript
function foo() {
  console.log('invoked!');
}
window.foo();
```

- Standard Built-in Object(표준 빌트인 객체)도 역시 전역 객체의 자식 객체이다. 전역 객체의 자식 객체를 사용할 때 전역 객체의 기술은 생략할 수 있으므로 표준 빌트인 객체도 전역 객체의 기술을 생략할 수 있다. 

``` javascript
// window.alert('Hello world!');
alert('Hello world!');
```

# 1. 전역 프로퍼티(Global property)
전역 프로퍼티는 전역 객체의 프로퍼티를 의미한다. 애플리케이션 전역에서 사용하는 값들을 나타내기 위해 사용한다. 전역 프로퍼티는 간단한 값이 대부분이며 다른 프로퍼티나 메소드를 가지고 있지 않다. 

## 1.1 Infinity
Infinity 프로퍼티는 양/음의 무한대를 나타내는 숫자값 Infinity를 갖는다. 

``` javascript
console.log(window.Infinity); // Infinity

console.log(3/0);  // Infinity
console.log(-3/0); // -Infinity
console.log(Number.MAX_VALUE * 2); // 1.7976931348623157e+308 * 2
console.log(typeof Infinity); // number
```

## 1.2 NaN
NaN 프로퍼티는 숫자가 아님(Not-a-Number)을 나타내는 숫자값 NaN을 갖는다. NaN 프로퍼티는 Number.NaN 프로퍼티와 같다. 

``` javascript
console.log(window.NaN); // NaN

console.log(Number('xyz')); // NaN
console.log(1 * 'string');  // NaN
console.log(typeof NaN);    // number
```

## 1.3 undefined 
undefined 프로퍼티는 원시 타입 undefined를 값으로 갖는다. 

``` javascript
console.log(window.undefined); // undefined

var foo;
console.log(foo); // undefined
console.log(typeof undefined); // undefined
```