---
title: js-day22-Math
date: 2021-10-29 22:37:38
    - javascript 
    - Math
categories: 
    - javascript
---
# Math
Math 객체는 수학 상수와 함수를 위한 프로퍼티와 메소드를 제공하는 빌트인 객체이다. Math 객체는 생성자 함수가 아니다. 따라서 Math 객체는 정적(static) 프로퍼티와 메소드만을 제공한다.

사용 빈도가 높은 프로퍼티와 메소드만을 설명한다.

# 1. Math Property
## 1.1 Math.PI
PI 값(π ≈ 3.141592653589793)을 반환한다.

``` javascript
Math.PI; // 3.141592653589793
```

# 2. Math  Method
## 2.1 Math.abs(x:number): number
인수의 절댓값(absolute value)을 반환한다. 절댓값은 반드시 0 또는 양수이어야 한다.

``` javascript
Math.abs(-1);       // 1
Math.abs('-1');     // 1
Math.abs('');       // 0
Math.abs([]);       // 0
Math.abs(null);     // 0
Math.abs(undefined);// NaN
Math.abs({});       // NaN
Math.abs('string'); // NaN
Math.abs();         // NaN
```

## 2.2 Math.round(x:number): number
인수의 소수점 이하를 반올림한 정수를 반환한다.

``` javascript
Math.round(1.4);  // 1
Math.round(1.6);  // 2
Math.round(-1.4); // -1
Math.round(-1.6); // -2
Math.round(1);    // 1
Math.round();     // NaN
```

## 2.3 Math.ceil(x:number): number
인수의 소수점 이하를 올림한 정수를 반환한다.

``` javascript
Math.ceil(1.4);  // 2
Math.ceil(1.6);  // 2
Math.ceil(-1.4); // -1
Math.ceil(-1.6); // -1
Math.ceil(1);    // 1
Math.ceil();     // NaN
```

## 2.4 Math.floor(x:number): number
인수의 소수점 이하를 내림한 정수를 반환한다. Math.ceil의 반대 개념이다.

- 양수인 경우, 소수점 이하를 떼어 버린 다음 정수를 반환한다.
- 음수인 경우, 소수점 이하를 떼어 버린 다음 -1을 한 정수를 반환한다.

``` javascript
Math.floor(1.9);  // 1
Math.floor(9.1);  // 9
Math.floor(-1.9); // -2
Math.floor(-9.1); // -10
Math.floor(1);    // 1
Math.floor();     // NaN
```

## 2.5 Math.sqrt(x:number): number
인수의 제곱근을 반환한다.

``` javascript
Math.sqrt(9);  // 3
Math.sqrt(-9); // NaN
Math.sqrt(2);  // 1.414213562373095
Math.sqrt(1);  // 1
Math.sqrt(0);  // 0
Math.sqrt();   // NaN
```

## 2.6 Math.random(): number
임의의 부동 소수점을 반환한다. 반환된 부동 소수점은 0부터 1 미만이다. 즉, 0은 포함되지만 1은 포함되지 않는다.

``` javascript
Math.random(); // 0 ~ 1 미만의 부동 소수점 (0.8208720231391746)

// 1 ~ 10의 랜덤 정수 취득
// 1) Math.random로 0 ~ 1 미만의 부동 소수점을 구한 다음, 10을 곱해 0 ~ 10 미만의 부동 소수점을 구한다.
// 2) 0 ~ 10 미만의 부동 소수점에 1을 더해 1 ~ 10까지의 부동 소수점을 구한다.
// 3) Math.floor으로 1 ~ 10까지의 부동 소수점의 소수점 이하를 떼어 버린 다음 정수를 반환한다.
const random = Math.floor((Math.random() * 10) + 1);
console.log(random); // 1 ~ 10까지의 정수
```

## 2.7 Math.pow(x:number, y:number): number
첫번째 인수를 밑(base), 두번째 인수를 지수(exponent)로하여 거듭제곱을 반환한다.

``` javascript
Math.pow(2, 8);  // 256
Math.pow(2, -1); // 0.5
Math.pow(2);     // NaN

// ES7(ECMAScript 2016) Exponentiation operator(거듭 제곱 연산자)
2 ** 8; // 256
```

## 2.8 Math.max(..values: number[]): number
인수 중에서 가장 큰 수를 반환한다. 

``` javascript
Math.max(1, 2, 3); // 3

// 배열 요소 중에서 최대값 취득
const arr = [1, 2, 3];
const max = Math.max.apply(null, arr); // 3

// ES6 Spread operator
Math.max(...arr); // 3
```

## 2.9 Math.min(…values: number[]): number
인수 중에서 가장 작은 수를 반환한다.

``` javascript
Math.min(1, 2, 3); // 1

// 배열 요소 중에서 최소값 취득
const arr = [1, 2, 3];
const min = Math.min.apply(null, arr); // 1

// ES6 Spread operator
Math.min(...arr); // 1
```

# Reference
[poiemaweb.com/js-math](https://poiemaweb.com/js-math)

