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

# 3. Number Method
## 3.1 Number.isFinite(testValue:number): boolean
매개변수에 전달된 값이 정상적인 유한수인지를 검사하여 그 결과를 Boolean으로 반환한다. 


``` javascript
/**
 * @param {any} testValue - 검사 대상 값. 암묵적 형변환되지 않는다.
 * @return {boolean}
 */
Number.isFinite(testValue)
```

Number.isFinite()는 전역 함수 isFinite()와 차이가 있다. 전역 함수 isFinite()는 인수를 숫자로 변환하여 검사를 수행하지만 Number.isFinite()는 인수를 변환하지 않는다. 따라서 숫자가 아닌 인수가 주어졌을 때 반환값은 언제나 false가 된다. 

``` javascript
Number.isFinite(Infinity)  // false
Number.isFinite(NaN)       // false
Number.isFinite('Hello')   // false
Number.isFinite('2005/12/12')   // false

Number.isFinite(0)         // true
Number.isFinite(2e64)      // true
Number.isFinite(null)      // false. isFinite(null) => true
```

## 3.2 Number.isInteger(testValue:number):boolean
매개변수에 전달된 값이 정수(Integer)인지 검사하여 그 결과를 Boolean으로 반환한다. 검사전에 인수를 숫자로 변환하지 않는다. 

``` javascript
/**
 * @param {any} testValue - 검사 대상 값. 암묵적 형변환되지 않는다.
 * @return {boolean}
 */
Number.isInteger(testValue)
```

``` javascript
Number.isInteger(123)   //true
Number.isInteger(-123)  //true
Number.isInteger(5-2)   //true
Number.isInteger(0)     //true
Number.isInteger(0.5)   //false
Number.isInteger('123') //false
Number.isInteger(false) //false
Number.isInteger(Infinity)  //false
Number.isInteger(-Infinity) //false
Number.isInteger(0 / 0) //false
```

## 3.3 Number.isNaN(testValue:number):boolean
매개변수에 전달된 값이 NaN인지를 검사하여 그 결과를 Boolean으로 반환한다. 

``` javascript
/**
 * @param {any} testValue - 검사 대상 값. 암묵적 형변환되지 않는다.
 * @return {boolean}
 */
Number.isNaN(testValue)
```

Number.isNaN()는 전역함수 isNaN()와 차이가 있다. 전역 함수 isNaN()는 인수를 숫자로 변환하여 검사를 수행하지만 Number.isNaN()는 인수를 변환하지 않는다. 따라서 숫자가 아닌 인수가 주어졌을 때 반환값은 언제나 false가 된다.

``` javascript
Number.isNaN(NaN)       // true
Number.isNaN(undefined) // false. undefined → NaN. isNaN(undefined) → true.
Number.isNaN({})        // false. {} → NaN.        isNaN({}) → true.
Number.isNaN('blabla')  // false. 'blabla' → NaN.  isNaN('blabla') → true.

Number.isNaN(true)      // false
Number.isNaN(null)      // false
Number.isNaN(37)        // false
Number.isNaN('37');     // false
Number.isNaN('37.37');  // false
Number.isNaN('');       // false
Number.isNaN(' ');      // false
Number.isNaN(new Date())             // false
Number.isNaN(new Date().toString())  // false. String → NaN. isNaN(String) → true.
```

## 3.4 Number.isSafeInteger(testValue:number):boolean
매개변수에 전달된 값이 안전한(safe) 정수값인지 검사하여 그 결과를 Boolean으로 반환한다. 안전한 정수값은 -(2^53 - 1)와 2^53 - 1 사이의 정수값이다. 검사전에 인수를 숫자로 변환하지 않는다.

``` javascript
/**
 * @param {any} testValue - 검사 대상 값. 암묵적 형변환되지 않는다.
 * @return {boolean}
 */
Number.isSafeInteger(testValue)
```

``` javascript
Number.isSafeInteger(123)   //true
Number.isSafeInteger(-123)  //true
Number.isSafeInteger(5-2)   //true
Number.isSafeInteger(0)     //true
Number.isSafeInteger(1000000000000000)  // true
Number.isSafeInteger(10000000000000001) // false
Number.isSafeInteger(0.5)   //false
Number.isSafeInteger('123') //false
Number.isSafeInteger(false) //false
Number.isSafeInteger(Infinity)  //false
Number.isSafeInteger(-Infinity) //false
Number.isSafeInteger(0 / 0) //false
```

## 3.5 Number.prototype.toExponential(fractionDigits?: number): string
대상을 지수 표기법으로 변환하여 문자열로 반환한다. 지수 표기법이란 매우 큰 숫자를 표기할 때 주로 사용하며 e(Exponent) 앞에 있는 숫자에 10의 n승이 곱하는 형식으로 수를 나타내는 방식이다.

``` code  
1234 = 1.234e+3
```

``` javascript
/**
 * @param {number} [fractionDigits] - 0~20 사이의 정수값으로 소숫점 이하의 자릿수를 나타낸다. 옵션으로 생략 가능하다.
 * @return {string}
 */
numObj.toExponential([fractionDigits])
```

``` javascript
var numObj = 77.1234;

console.log(numObj.toExponential());  // logs 7.71234e+1
console.log(numObj.toExponential(4)); // logs 7.7123e+1
console.log(numObj.toExponential(2)); // logs 7.71e+1
console.log(77.1234.toExponential()); // logs 7.71234e+1
console.log(77.toExponential());      // SyntaxError: Invalid or unexpected token
console.log(77 .toExponential());     // logs 7.7e+1
```

정수 리터럴과 함께 메소드를 사용할 경우
아래의 예제를 실행하면 에러가 발생한다.

``` javascript
77.toString(); // SyntaxError: Invalid or unexpected token
```

숫자 뒤의 .은 의미가 모호하다. 소수 구분 기호일 수도 있고 객체 프로퍼티에 접근하기 위한 마침표 표기법(Dot notation)일 수도 있다. 따라서 자바스크립트 엔진은 숫자 뒤의 .을 부동 소수점 숫자의 일부로 해석한다. 그러나 77.toString()은 숫자로 해석할 수 없으므로 에러(SyntaxError: Invalid or unexpected token)가 발생한다.

``` javascript
1.23.toString (); // '1.23'
```

위 예제의 경우, 숫자 뒤의 첫 번째 . 뒤에는 숫자가 이어지므로 .은 명백하게 부동 소수점 숫자의 일부이다. 숫자에 소수점은 하나만 존재하므로 두 번째 .은 마침표 표기법(Dot notation)으로 해석된다.

따라서 정수 리터럴과 함께 메소드를 사용할 경우, 아래의 방법을 권장한다.

``` javascript
(77).toString();//'77'
```

또한 아래 방법도 허용되기는 한다. 자바스크립트 숫자는 정수 부분과 소수 부분 사이에 공백을 포함할 수 없다. 따라서 숫자 뒤의 . 뒤에 공백이 오면 .을 마침표 표기법(Dot notation)으로 해석하기 때문이다.

``` javascript
77 .toString(); // '77'
```

## 3.6 Number.prototype.toFixed(fractionDigits?: number): string

매개변수로 지정된 소숫점자리를 반올림하여 문자열로 반환한다.

``` javascript
/**
 * @param {number} [fractionDigits] - 0~20 사이의 정수값으로 소숫점 이하 자릿수를 나타낸다. 기본값은 0이며 옵션으로 생략 가능하다.
 * @return {string}
 */
numObj.toFixed([fractionDigits])
```

``` javascript
var numObj = 12345.6789;

// 소숫점 이하 반올림
console.log(numObj.toFixed());   // '12346'
// 소숫점 이하 1자리수 유효, 나머지 반올림
console.log(numObj.toFixed(1));  // '12345.7'
// 소숫점 이하 2자리수 유효, 나머지 반올림
console.log(numObj.toFixed(2));  // '12345.68'
// 소숫점 이하 3자리수 유효, 나머지 반올림
console.log(numObj.toFixed(3));  // '12345.679'
// 소숫점 이하 6자리수 유효, 나머지 반올림
console.log(numObj.toFixed(6));  // '12345.678900'
```

## 3.7 Number.prototype.toPrecision(precision?: number): string
매개변수로 지정된 전체 자릿수까지 유효하도록 나머지 자릿수를 반올림하여 문자열로 반환한다. 지정된 전체 자릿수로 표현할 수 없는 경우 지수 표기법으로 결과를 반환한다.

``` javascript
/**
 * @param {number} [precision] - 1~21 사이의 정수값으로 전체 자릿수를 나타낸다. 옵션으로 생략 가능하다.
 * @return {string}
 */
numObj.toPrecision([precision])
```

``` javascript
var numObj = 15345.6789;

// 전체자리수 유효
console.log(numObj.toPrecision());   // '12345.6789'
// 전체 1자리수 유효, 나머지 반올림
console.log(numObj.toPrecision(1));  // '2e+4'
// 전체 2자리수 유효, 나머지 반올림
console.log(numObj.toPrecision(2));  // '1.5e+4'
// 전체 3자리수 유효, 나머지 반올림
console.log(numObj.toPrecision(3));  // '1.53e+4'
// 전체 6자리수 유효, 나머지 반올림
console.log(numObj.toPrecision(6));  // '12345.7'
```

## 3.8 Number.prototype.toString(radix?: number): string
숫자를 문자열로 변환하여 반환한다.

``` javascript
/**
 * @param {number} [radix] - 2~36 사이의 정수값으로 진법을 나타낸다. 옵션으로 생략 가능하다.
 * @return {string}
 */
numObj.toString([radix])
```

``` javascript
var count = 10;
console.log(count.toString());   // '10'
console.log((17).toString());    // '17'
console.log(17 .toString());     // '17'
console.log((17.2).toString());  // '17.2'

var x = 16;
console.log(x.toString(2));       // '10000'
console.log(x.toString(8));       // '20'
console.log(x.toString(16));      // '10'

console.log((254).toString(16));  // 'fe'
console.log((-10).toString(2));   // '-1010'
console.log((-0xff).toString(2)); // '-11111111'
```

## 3.9 Number.prototype.valueOf(): number
Number 객체의 원시 타입 값(primitive value)을 반환한다.

``` javascript
var numObj = new Number(10);
console.log(typeof numObj); // object

var num = numObj.valueOf();
console.log(num);           // 10
console.log(typeof num);    // number
```

# Reference
[poiemaweb.com/js-number](https://poiemaweb.com/js-number)

