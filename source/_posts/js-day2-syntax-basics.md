---
title: js-day2-syntax-basics
date: 2021-06-01 17:01:44
    - javascript 
    - syntax
    - basic
categories: 
    - javascript
---

### Syntax Basics
## 자바스크립트의 기본 문법
# 1. 변수
변수(Variable)는 값(Value)을 저장(할당)하고 그 저장된 값을 참조하기 위해 사용한다. 한번 쓰고 버리는 값이 아닌 유지(캐싱)할 필요가 있는 값은 변수에 담아 사용한다. 이름을 통해 값의 의미를 명확히 할 수 있어 코드의 가독성이 좋아진다. 

변수는 위치(주소)를 기억하는 저장소이다. 위치란 메모리 상의 주소(address)를 의미한다. 즉, 변수란 메모리 주소(Memory address)에 접근하기 위해 사람이 이해할 수 있는 언어로 지정한 식별자(identifier)이다. 

변수를 선언할 때 **var** 키워드를 사용한다. 할당 연산자 **=** 는 변수에 값을 할당하기 위해 사용한다. 

아래의 예에서 x는 변수로 선언되었고 변수 x에는 정수값 6이 할당되었다. 

``` javascript
var x;
x = 6;
```

# 2. 값

``` javascript
var str = 'Hello World';
```

위 예제는 str이라는 이름의 변수를 선언하고 문자열 리터럴 'Hello World'를 값으로 할당하였다. 이때 문자열 리터럴 'Hello World'는 문자열 타입의 값이다. 

|용어|의미|
|----|----|
|데이터 타입(Data Type)|프로그래밍 언어에서 사용할 수 있는 값의 종류|
|변수(Varialble)|값이 저장된 메모리 공간의 주소를 가르키는 식별자(identifier)|
|리터럴(literal)|소스코드 안에서 직접 만들어 낸 상수 값 자체를 말하며 값을 구성하는 최소 단위|

값(Value)은 프로그램에 의해 조작될 수 있는 대상을 말한다. 값은 다양한 방법으로 생성할 수 있다. 가장 간단한 방법은 리터럴 표기법(literal notation)을 사용하는 것이다. 

``` javascript
// 숫자 리터럴
10.50
1001

// 문자열 리터럴
'Hello'
"World"

// 불리언 리터럴
true
false

// null 리터럴
null

// undefined 리터럴
undefined

// 객체 리터럴
{ name: 'Lee', gender: 'male' }

// 배열 리터럴
[ 1, 2, 3 ]

// 정규표현식 리터럴
/ab+c/

// 함수 리터럴
function() {}
```

숫자, 문자열, 불리언과 같은 원시 타입의 리터럴은 다양한 연산자의 피연산자가 되어 하나의 값으로 평가될 수 있다. 이렇게 리터럴은 연산에 의해 하나의 값이 될 수 있다. 

``` javascript
// 산술연산
10.50 + 1001
```

자바스크립트의 모든 값은 데이터 타입을 갖는다. 자바스크립트는 7가지 데이터 타입을 제공한다. 

- 원시 타입(primitive data type)
>- number
>- string
>- boolean
>- null
>- undefined
>- symbol (new in ECMAScript 6)

- 객체 타입(object data type)
>- object

자바스크립트는 C나 Java외는 다르게 변수를 선언할 때 데이터 타입을 미리 지정하지 않는다. 다시 말해, 변수에 할당된 값의 타입에 의해 동적으로 변수의 타입이 결정된다. 이를 동적 타이핑이라 하며 자바스크립트가 다른 프로그래밍 언어와 구별되는 특징 중 하나이다. 

``` javascript
// Number
var num1 = 1001;
var num2 = 10.50;

// String
var string1 = 'Hello';
var string2 = "World";

// Boolean
var bool = true;

// null
var foo = null;

// undefined
var bar;

// Object
var obj = { name: 'Lee', gender: 'male' };

// Array
var array = [ 1, 2, 3 ];

// function
var foo = function() {};
```

# 연산자 
연산자(Operator)는 하나 이상의 표현식을 대상으로 산술, 할당, 비교, 논리, 타입 연산 등을 수행해 하나의 값을 만든다. 이때 연산의 대상을 피연산자(Operand)라 한다. 

``` javascript
// 산술 연산자
var area = 5 * 4; // 20

// 문자열 연결 연산자
var str = 'My name is ' + 'Lee'; // "My name is Lee"

// 할당 연산자
var color = 'red'; // "red"

// 비교 연산자
var foo = 3 > 5; // false

// 논리 연산자
var bar = (5 > 3) && (2 < 4);  // true

// 타입 연산자
var type = typeof 'Hi'; // "string"

// 인스턴스 생성 연산자
var today = new Date(); // (한국 표준시)
```

``` javascript
var foo = 1 + '10'; // '110'
var bar = 1 * '10'; // 10
```

# 4. 키워드 
키워드(keyword)는 수행할 동작을 규정한 것이다. 예를 들어 var 키워드는 새로운 변수를 생성할 것을 지시한다.

``` javascript
// 변수의 선언
var x = 5 + 6;

// 함수의 선언
function foo (arg) {
  // 함수 종료 및 값의 반환
  return ++arg;
}

var i = 0;
// 반복문
while (1) {
  if (i > 5) {
    // 반복문 탈출
    break;
  }
  console.log(i);
  i++;
}
```