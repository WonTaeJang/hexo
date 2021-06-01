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