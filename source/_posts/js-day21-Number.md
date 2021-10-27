---
title: js-day21-Number
date: 2021-10-27 16:52:20
    - javascript 
    - Number
categories: 
    - javascript
---

# Number 레퍼 객체
Number 객체는 원시 타입 number를 다룰 때 유용한 프로퍼티와 메소드를 제공하는 레퍼(wrapper) 객체이다. 변수 또는 객체의 프로퍼티가 숫자를 값으로 가지고 있다면 Number 객체의 별도 생성없이 Number 객체의 프로퍼티와 메소드를 사용할 수 있다.

원시 타입이 wrapper 객체의 메소드를 사용할 수 있는 이유는 원시 타입으로 프로퍼티나 메소드를 호출할 때 원시 타입과 연관된 wrapper 객체로 일시적으로 변환되어 프로토타입 객체를 공유하게 되기 때문이다.

``` javascript
var num = 1.5;
console.log(num.toFixed()); // 2
```

위에서 원시 타입을 담고 있는 변수 num이 Number.prototype.toFixed() 메소드를 호출할 수 있는 것은 변수 num의 값이 일시적으로 wrapper객체로 변환되었기 때문이다.

# 1. Number Constructor
Number 객체는 Number() 생성자 함수를 통해 생성할 수 있다. 

``` javascript
new Number(value);
```

만일 인자가 숫자로 변환될 수 없다면 NaN을 반환한다.

``` javascript
var x = new Number(123);
var y = new Number('123');
var z = new Number('str');

console.log(x); // 123
console.log(y); // 123
console.log(z); // NaN
```

Number() 생성자 함수를 new 연산자를 붙이지 않아 생성자로 사용하지 않으면 Number 객체를 반환하지 않고 원시 타입 숫자를 반환한다. 이때 형 변환이 발생할 수 있다.

``` javascript
var x = Number('123');

console.log(typeof x, x); // number 123
```

일반적으로 숫자를 사용할 때는 원시 타입 숫자를 사용한다.

``` javascript
var x = 123;
var y = new Number(123);

console.log(x == y);  // true
console.log(x === y); // false

console.log(typeof x); // number
console.log(typeof y); // object
```

# 2. Number Property
정적(static)프로퍼티로 Number 객체를 생성할 필요없이 Number.propertyName의 형태로 사용한다. 

## 2.1 Number.EPSILON
Number.EPSILON은 JavaScript에서 표현할 수 있는 가장 작은 수이다. 이는 임의의 수와 그 수보다 큰 수 중 가장 작은 수와의 차이와 같다. Number.EPSILON은 약 2.2204460492503130808472633361816E-16 또는 2-52이다.

부동소수점 산술 연산 비교는 정확한 값을 기대하기 어렵다. 정수는 2진법으로 오차없이 저장이 가능하지만 부동소수점을 표현하는 가장 널리 쓰이는 표준인 IEEE 754은 2진법으로 변환시 무한소수가 되어 미세한 오차가 발생할 수밖에 없는 구조적 한계를 갖는다.

따라서 부동소수점의 비교는 Number.EPSILON을 사용하여 비교 기능을 갖는 함수를 작성하여야 한다.

``` javascript
console.log(0.1 + 0.2);        // 0.30000000000000004
console.log(0.1 + 0.2 == 0.3); // false!!!

function isEqual(a, b){
  // Math.abs는 절댓값을 반환한다.
  // 즉 a와 b의 차이가 JavaScript에서 표현할 수 있는 가장 작은 수인 Number.EPSILON보다 작으면 같은 수로 인정할 수 있다.
  return Math.abs(a - b) < Number.EPSILON;
}

console.log(isEqual(0.1 + 0.2, 0.3));
```

## 2.2 Number.MAX_VALUE
자바스크립트에서 사용 가능한 가장 큰 숫자(1.7976931348623157e+308)를 반환한다. MAX_VALUE보다 큰 숫자는 Infinity이다.

``` javascript
Number.MAX_VALUE; // 1.7976931348623157e+308

var num = 10;
num.MAX_VALUE;    // undefined

console.log(Infinity > Number.MAX_VALUE); // true
```

## 2.3 Number.MIN_VALUE
자바스크립트에서 사용 가능한 가장 작은 숫자(5e-324)를 반환한다. MIN_VALUE는 0에 가장 가까운 양수 값이다. MIN_VALUE보다 작은 숫자는 0으로 변환된다.

``` javascript
Number.MIN_VALUE; // 5e-324

var num = 10;
num.MIN_VALUE;    // undefined

console.log(Number.MIN_VALUE > 0); // true
```

## 2.4 Number.POSITIVE_INFINITY
양의 무한대 Infinity를 반환한다.
``` javascript
Number.POSITIVE_INFINITY // Infinity

var num = 10;
num.POSITIVE_INFINITY;   // undefined
```

## 2.5 Number.NEGATIVE_INFINITY
음의 무한대 -Infinity를 반환한다.
``` javascript
Number.NEGATIVE_INFINITY // -Infinity

var num = 10;
num.NEGATIVE_INFINITY;   // undefined
```

## 2.6 Number.NaN
숫자가 아님(Not-a-Number)을 나타내는 숫자값이다. Number.NaN 프로퍼티는 window.NaN 프로퍼티와 같다.

``` javascript
console.log(Number('xyz')); // NaN
console.log(1 * 'string');  // NaN
console.log(typeof NaN);    // number
```

