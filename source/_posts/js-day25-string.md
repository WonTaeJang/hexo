---
title: js-day25-string
date: 2021-11-11 16:53:39
    - javascript 
    - string
categories: 
    - javascript
---

# String 레퍼 객체
String 객체는 원시 타입인 문자열을 다룰 때 유용한 프로퍼티와 메소드를 제공하는 레퍼(wrapper) 객체이다. 변수 또는 객체 프로퍼티가 문자열을 값으로 가지고 있다면 String 객체의 별도 생성없이 String 객체의 프로퍼티와 메소드를 사용할 수 있다.

원시타입이 wrapper 객체의 메소드를 사용할 수 있는 이유는 원시 타입으로 프로퍼티나 메소드를 호출할 때 원시 타입과 연관된 wrapper 객체로 일시적으로 변환되어 프로토타입 객체를 공유하게 되기 때문이다. 

``` javascript
const str = 'Hello world!';
console.log(str.toUpperCase()); // 'HELLO WORLD!'
```

위에서 원시 타입 문자열을 담고 있는 변수 str이 String.prototype.toUpperCase() 메소드를 호출할 수 있는 것은 변수 str의 값이 일시적으로 wrapper객체로 변환되었기 때문이다.

사용 빈도가 높은 String 객체의 프로퍼티와 메소드에 대해 살펴보도록 하자.

# 1. String Constructor 
String 객체는 String 생성자 함수를 통해 생성할 수 있다. 이때 전달된 인자는 모두 문자열로 변환된다. 

``` javascript
new String(value);
```

``` javascript
let strObj = new String('Lee');
console.log(strObj); // String {0: 'L', 1: 'e', 2: 'e', length: 3, [[PrimitiveValue]]: 'Lee'}

strObj = new String(1);
console.log(strObj); // String {0: '1', length: 1, [[PrimitiveValue]]: '1'}

strObj = new String(undefined);
console.log(strObj); // String {0: 'u', 1: 'n', 2: 'd', 3: 'e', 4: 'f', 5: 'i', 6: 'n', 7: 'e', 8: 'd', length: 9, [[PrimitiveValue]]: 'undefined'}
```

new 연산자를 사용하지 않고 String 생성자 함수를 호출하면 String 객체가 아닌 문자열 리터럴을 반환한다. 이때 형 변환이 발생할 수 있다.

``` javascript
var x = String('Lee');

console.log(typeof x, x); // string Lee
```

일반적으로 문자열을 사용할 때는 원시타입 문자열을 사용한다. 

``` javascript
const str = 'Lee';
const strObj = new String('Lee');

console.log(str == strObj);  // true
console.log(str === strObj); // false

console.log(typeof str);    // string
console.log(typeof strObj); // object
```

# 2. String Property
## 2.1 String length
문자열 내의 문자 개수를 반환한다. String 객체는 length 프로퍼티를 소유하고 있으므로 유사 배열 객체이다. 

``` javascript
const str1 = 'Hello';
console.log(str1.length); // 5

const str2 = '안녕하세요!';
console.log(str2.length); // 6
```

# 3. String Method
String 객체의 모든 메소드는 언제나 새로운 문자열을 반환한다. 문자열은 변경 불가능(immutable)한 원시 값이기 때문이다. 

## 3.1 String.prototype.charAt(pos:number): string
인수로 전달한 index를 사용하여 index에 해당하는 위치의 문자를 반환한다. index는 0~ (문자열 길이 -1)사이의 정수이다. 지정한 index가 문자열의 범위(0 ~ (문자열 길이 -1))를 벗어난 경우 빈문자열을 반환한다.

``` javascript
const str = 'Hello';

console.log(str.charAt(0)); // H
console.log(str.charAt(1)); // e
console.log(str.charAt(2)); // l
console.log(str.charAt(3)); // l
console.log(str.charAt(4)); // o
// 지정한 index가 범위(0 ~ str.length-1)를 벗어난 경우 빈문자열을 반환한다.
console.log(str.charAt(5)); // ''

// 문자열 순회. 문자열은 length 프로퍼티를 갖는다.
for (let i = 0; i < str.length; i++) {
  console.log(str.charAt(i));
}

// String 객체는 유사 배열 객체이므로 배열과 유사하게 접근할 수 있다.
for (let i = 0; i < str.length; i++) {
  console.log(str[i]); // str['0']
}
```

## 3.2 String.prototype.concat(...string: string[]): string
인수로 전달한 1개 이상의 문자열과 연결하여 새로운 문자열을 반환한다. 

concat 메소드를 사용하는 것보다는 +, += 할당 연산자를 사용하는 것이 성능상 유리하다. 

``` javascript
/**
 * @param {...string} str - 연결할 문자열
 * @return {string}
 */
str.concat(str1[,str2,...,strN])
```

``` javascript
console.log('Hello '.concat('Lee')); // Hello Lee
```