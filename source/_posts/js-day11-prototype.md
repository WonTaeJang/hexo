---
title: js-day11-prototype
date: 2021-08-04 10:08:27
    - javascript 
    - prototype
categories: 
    - javascript
---

# 1. Prototype 객체
Java, C++과 같은 클래스 기반 객체지향 프로그래밍 언어와 달리 자바스크립트는 프로토타입 기반 객체지향 프로그래밍 언어이다. 따라서 자바스크립트의 동작 원리를 이해하기 위해서는 프로토타입의 개념을 잘 이해하고 있어야 한다.

클래스 기반 객체지향 프로그래밍 언어는 객체 생성 이전에 클래스를 정의하고 이를 통해 객체(인스턴스)를 생성한다. 하지만 프로토타입 기반 객체지향 프로그래밍 언어는 클래스 없이(Class-less)도 객체를 생성할 수 있다. 

- [자바스크립트의 객체 생성방법](https://wontaejang.github.io/2021/06/30/js-day7-object/)

자바스크립트의 모든 객체는 자신의 부모 역할을 담당하는 객체와 연결되어 있다. 그리고 이것은 마치 객체 지향의 상속 개념과 같이 부모 객체의 프로퍼티 또는 메소드를 상속받아 사용할 수 있게 한다. 이러한 부모 객체를 Prototype(프로토타입)객체 또는 줄여서 Prototype(프로토타입)이라 한다. 

Prototype 객체는 생성자 함수에 의해 생성된 각각의 객체에 공유 프로퍼티를 제공하기 위해 사용한다. 

``` javascript
var student = {
  name: 'Lee',
  score: 90
};

// student에는 hasOwnProperty 메소드가 없지만 아래 구문은 동작한다.
console.log(student.hasOwnProperty('name')); // true

console.dir(student);
```

[ECMAScript spec](https://tc39.es/ecma262/#sec-ordinary-and-exotic-objects-behaviours)에서는 자바스크립트의 모든 객체는 [[Prototype]]이라는 이터널 슬롯(internal slot)를 가진다. [[Prototype]]의 값은 null 또는 객체이며 상속을 구현하는데 사용된다. [[Prototype]] 객체의 데이터 프로퍼티는 get 액세스를 위해 상속되어 자식 객체의 프로퍼티처럼 사용할 수 있다. 하지만 set 액세스는 허용되지 않는다. 라고 되어있다. 

[[Prototype]]의 값은 Prototype(프로토타입)객체이며 &#95;&#95;proto&#95;&#95; accessor property로 접근할 수 있다. &#95;&#95;proto&#95;&#95;프로퍼티에 접근하면 내부적으로 [Object.getPrototypeOf](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf)가 호출되어 프로토타입 객체를 반환한다. 

student 객체는 &#95;&#95;proto&#95;&#95; 프로퍼티로 자신의 부모 객체(프로토타입 객체)인 Object.prototype을 가리키고 있다. 

``` javascript
var student = {
  name: 'Lee',
  score: 90
}
console.log(student.__proto__ === Object.prototype); // true
```

객체를 생성할 때 프로토타입은 결정된다. 결정된 프로토타입 객체는 다른 임의의 객체로 변경할 수 있다. 이것은 부모 객체인 프로토타입을 동적으로 변경할 수 있다는 것을 의미한다. 이러한 특징을 활용하여 객체의 상속을 구현할 수 있다. 

# 2. [[Prototype]] vs prototype 프로퍼티
모든 객체는 자신의 프로토타입 객체를 가리키는 [[Prototype]] 인터널 슬롯(internal slot)을 갖으며 상속을 위해 사용된다. 

함수도 객체이므로 [[Prototype]] 인터널 슬롯을 갖는다. 그런데 함수 객체는 일반 객체와는 달리 prototype 프로퍼티도 소유하게 된다. 

> 주의해야 할 것은 prototype 프로퍼티는 프로토타입 객체를 가리키는 [[Prototype]] 인터널 슬롯은 다르다는 것이다. prototype 프로퍼티와 [[Prototype]]은 모두 프로토타입 객체를 가리키지만 관점의 차이가 있다.

``` javascript
function Person(name) {
  this.name = name;
}

var foo = new Person('Lee');

console.dir(Person); // prototype 프로퍼티가 있다.
console.dir(foo);    // prototype 프로퍼티가 없다.
```

- [[Prototype]]
    - 함수 객체만 가지고 있는 프로퍼티이다. 
    - **함수 객체가 생성자로 사용될 때 이 함수를 통해 생성 될 객체의 부모 역할을 하는 객체(프로토타입 객체)를 가리킨다.**

``` javascript
console.log(Person.prototype === foo.__proto__);
```

# 3. constructor 프로퍼티
프로토타입 객체는 constructor 프로퍼티를 갖는다. 이 constructor 프로퍼티는 객체의 입장에서 자신을 생성한 객체를 가리킨다. 

예를 들어 Person() 생성자 함수에 의해 생성된 객체를 foo라 하자. 이 foo 객체를 생성한 객체는 Person() 생성자 함수이다. 이때 foo 객체 입장에서 자신을 생성한 객체는 Person() 생성자 함수이며, foo 객체의 프로토타입 객체는 Person.prototype이다. 따라서 프로토타입 객체 Person.prototype 의 constructor 프로퍼티는 Person() 생성자 함수를 가리킨다. 

``` javascript
function Person(name) {
  this.name = name;
}

var foo = new Person('Lee');

// Person() 생성자 함수에 의해 생성된 객체를 생성한 객체는 Person() 생성자 함수이다.
console.log(Person.prototype.constructor === Person);

// foo 객체를 생성한 객체는 Person() 생성자 함수이다.
console.log(foo.constructor === Person);

// Person() 생성자 함수를 생성한 객체는 Function() 생성자 함수이다.
console.log(Person.constructor === Function);
```

# 4.Prototype chain 
자바스크립트는 특정 객체의 프로퍼티나 메소드에 접근하려고 할 때 해당 객체에 접근하려는 프로퍼티 또는 메소드가 없다면 [[Prototype]]이 가리키는 링크를 따라 자신의 부모 역할을 하는 프로토타입 객체의 프로퍼티나 메소드를 차례대로 검색한다. 이것을 프로토타입 체인이라 한다. 

``` javascript
var student = {
  name: 'Lee',
  score: 90
}

// Object.prototype.hasOwnProperty()
console.log(student.hasOwnProperty('name')); // true
```

student 객체는 hasOwnProperty 메소드를 가지고 있지 않으므로 에러가 발행하여야 하나 정상적으로 결과가 출력되었다. 이는 student 객체의 [[Prototype]]이 가리키는 링크를 따라가서 student 객체의 부모 역할을 하는 프로토타입 객체(Object.prototype)의 메소드 hasOwnProterty를 호출하였기 때문에 가능한 것이다. 

``` javascript
var student = {
  name: 'Lee',
  score: 90
}
console.dir(student);
console.log(student.hasOwnProperty('name')); // true
console.log(student.__proto__ === Object.prototype); // true
console.log(Object.prototype.hasOwnProperty('hasOwnProperty')); // true
```

## 4.1 객체 리터럴 방식으로 생성된 객체의 프로토타입 체인 
객체생성 방법은 3가지가 있다. 
- 객체 리터럴
- 생성자 함수
- Object() 생성자 함수

객체 리터럴 방식으로 생성된 객체는 결국 내장함수(Built-in)인 Object() 생성자 함수로 객체를 생성하는 것을 단순화시킨 것이다. 자바스크립트 엔진은 객체 리터럴로 객체를 생성하는 코드를 만나면 내부적으로 Object() 생성자 함수를 사용하여 객체를 생성한다. 

Object() 생성자 함수는 물론 함수이다. 따라서 함수 객체인 Object() 생성자 함수는 일반 객체와 달리 prototype 프로퍼티가 있다. 
- prototype 프로퍼티는 함수 객체가 생성자로 사용될 때 이 함수를 통해 생성된 객체의 부모 역할을 하는 객체, 즉 프로토타입 객체를 가리킨다. 
- [[Prototype]]은 객체의 입장에서 자신의 부모 역할을 하는 객체, 즉 프로토타입 객체를 가리킨다. 

``` javascript
var person = {
  name: 'Lee',
  gender: 'male',
  sayHello: function(){
    console.log('Hi! my name is ' + this.name);
  }
};

console.dir(person);

console.log(person.__proto__ === Object.prototype);   // ① true
console.log(Object.prototype.constructor === Object); // ② true
console.log(Object.__proto__ === Function.prototype); // ③ true
console.log(Function.prototype.__proto__ === Object.prototype); // ④ true
```

> 결론적으로 객체 리터럴을 사용하여 객체를 생성한 경우, 그 객체의 프로토타입 객체는 Object.prototype이다. 

## 4.2 생성자 함수로 생성된 객체의 프로토타입 체인
생성자 함수로 객체를 생성하기 위해서는 우선 생성자 함수를 정의하여야 한다. 

함수를 정의하는 방식은 3가지가 있다. 
- 함수선언식(Function declaration)
- 함수표현식(Funciton expression)
- Funciton() 생성자 함수

함수표현식으로 함수를 정의할 때 함수 리터럴 방식을 사용한다. 

``` javascript
var square = function(number) {
  return number * number;
};
```

함수 선언식의 경우 자바스크립트 엔진이 내부적으로 기명 함수표현식으로 변환한다. 

``` javascript
var square = function square(number) {
  return number * number;
};
```

결국 함수선언식, 함수표현식 모두 함수 리터럴 방식을 사용한다. 함수 리터럴 방식은 Function() 생성자 함수로 함수를 생성하는 것을 단순화 시킨것이다. 

> 즉, 3자기 함수 정의 방식은 결국 Function() 생성자 함수를 통해 함수 객체를 생성한다, 따라서 어떠한 방식으로 함수 객체를 생성하여도 모든 함수 객체의 prototype 객체는 Function.prototype이다. 생성자 함수도 함수 객체이므로 생성자 함수의 prototyupe 객체는 Function.prototype이다. 

이제 객체의 관점에서 prototype 객체를 살펴보자. 

객체를 생성하는 방식은 3가지가 있다. 3가지 객체 생성 방식에 의해 생성된 객체의 prototype 객체를 정리해 보면 아래와 같다. 

|객체 생성 방식|엔진의 객체 생성|인스턴스의 prototype 객체|
|--------------|----------------|------------------------|
|객체 리터럴|Object() 생성자 함수|Object.prototype|
|Object() 생성자 함수|Object() 생성자 함수|Object.prototype|
|생성자 함수|생성자 함수|생성자 함수 이름.prototype|

``` javascript
function Person(name, gender) {
  this.name = name;
  this.gender = gender;
  this.sayHello = function(){
    console.log('Hi! my name is ' + this.name);
  };
}

var foo = new Person('Lee', 'male');

console.dir(Person);
console.dir(foo);

console.log(foo.__proto__ === Person.prototype);                // ① true
console.log(Person.prototype.__proto__ === Object.prototype);   // ② true
console.log(Person.prototype.constructor === Person);           // ③ true
console.log(Person.__proto__ === Function.prototype);           // ④ true
console.log(Function.prototype.__proto__ === Object.prototype); // ⑤ true
```

foo 객체의 프로토타입 객체 Person.prototype 객체와 Person() 생성자 함수의 프로토타입 객체인 Function.prototype의 프로토타입 객체는 Object.prototype 객체이다.

이는 객체 리터럴 방식이나 생성자 함수 방식이나 결국은 모든 객체의 부모 객체인 Object.prototype 객체에서 프로토타입 체인이 끝나기 때문이다. 이때 Object.prototype 객체를 프로토타입 체인의 종점(End of prototype chain)이라 한다.