---
title: js-day18-Object-Oriented-Programming
date: 2021-09-30 22:35:40
    - javascript 
    - Object-Oriented-Programming
categories: 
    - javascript
---

# 1. 객체지향 프로그래밍(Object-Oriented Programming) 개요

오늘날 많은 유명한 프로그래밍 언어(Java, C++, C#, Python, PHP, Ruby, Object-C)는 객체지향 프로그래밍을 지원한다. “객체지향”이라는 개념은 불행히도 명확한 정의가 없는 것이 특징이다. 우리가 어떠한 개념을 이해하려할 때, 그 개념의 특성(attribute, property)을 통해 이해하는 것처럼 객체지향도 객체지향의 특성을 통해 이해할 수밖에 없다.

객체지향 프로그래밍은 실세계에 존재하고 인지하고 있는 객체(Object)를 소프트웨어의 세계에서 표현하기 위해 객체의 핵심적인 개념 또는 기능만을 추출하는 추상화(abstraction)를 통해 모델링하려는 프로그래밍 패러다임을 말한다. 다시 말해, 우리가 주변의 실세계에서 사물을 인지하는 방식을 프로그래밍에 접목하려는 사상을 의미한다.

객체지향 프로그래밍은 함수들의 집합 혹은 단순한 컴퓨터의 명령어들의 목록이라는 전통적인 절차지향 프로그래밍과는 다른, 관계성있는 객체들의 집합이라는 관점으로 접근하는 소프트웨어 디자인으로 볼 수 있다.

각 객체는 메시지를 받을 수도 있고, 데이터를 처리할 수도 있으며, 또다른 객체에게 메시지를 전달할 수도 있다. 각 객체는 별도의 역할이나 책임을 갖는 작은 독립적인 기계 또는 부품으로 볼 수 있다.

객체지향 프로그래밍은 보다 유연하고 유지보수하기 쉬우며 확장성 측면에서서도 유리한 프로그래밍을 하도록 의도되었고, 대규모 소프트웨어 개발에 널리 사용되고 있다.

# 2. 클래스 기반 vs. 프로토타입 기반
## 2.1 클래스 기반 언어
클래스 기반 언어(Java, C++, C#, Python, PHP, Ruby, Object-C)는 클래스로 객체의 자료구조와 기능을 정의하고 생성자를 통해 인스턴스를 생성한다.

클래스란 같은 종류의 집단에 속하는 속성(attribute)과 행위(behavior)를 정의한 것으로 객체지향 프로그램의 기본적인 사용자 정의 데이터형(user define data type)이라고 할 수 있다. 결국 클래스는 객체 생성에 사용되는 패턴 혹은 청사진(blueprint)일 뿐이며 new 연산자를 통한 인스턴스화 과정이 필요하다.

모든 인스턴스는 오직 클래스에서 정의된 범위 내에서만 작동하며 런타임에 그 구조를 변경할 수 없다. 이러한 특성은 정확성, 안정성, 예측성 측면에서 클래스 기반 언어가 프로토타입 기반 언어보다 좀 더 나은 결과를 보장한다.

아래의 예제는 Java로 구현된 클래스이다. Java는 class 키워드를 제공하고 이것으로 클래스를 정의한다. 생성자는 클래스명과 동일하며 메소드로 구현된다.

``` java
class Person {
  private String name;

  public Person(String name) {
    this.name = name;
  }

  public void setName(String name) {
    this.name = name;
  }

  public String getName() {
    return this.name;
  }

  public static void main(String[] args) {
    Person me = new Person("Lee");

    String name= me.getName();
    System.out.println(name); // Lee
  }
}
```

## 2.2 프로토타입 기반 언어
자바스크립트는 멀티-패러다임 언어로 명령형(imperative), 함수형(functional), 프로토타입 기반(prototype-based) 객체지향 언어다. 비록 다른 객체지향 언어들과의 차이점에 대한 논쟁들이 있긴 하지만, 자바스크립트는 강력한 객체지향 프로그래밍 능력들을 지니고 있다. 간혹 클래스가 없어서 객체지향이 아니라고 생각하는 사람들도 있으나 프로토타입 기반의 객체지향 언어다.

자바스크립트는 클래스 개념이 없고 별도의 객체 생성 방법이 존재한다.

- 객체 리터럴
- Object() 생성자 함수
- 생성자 함수

``` javascript
// 객체 리터럴
var obj1 = {};
obj1.name = 'Lee';

// Object() 생성자 함수
var obj2 = new Object();
obj2.name = 'Lee';

// 생성자 함수
function F() {}
var obj3 = new F();
obj3.name = 'Lee';
```

자바스크립트는 이미 생성된 인스턴스의 자료구조와 기능을 동적으로 변경할 수 있다는 특징이 있다. 객체 지향의 상속, 캡슐화(정보 은닉) 등의 개념은 프로토타입 체인과 클로저 등으로 구현할 수 있다.

클래스 기반 언어에 익숙한 프로그래머들은 이러한 프로토타입 기반의 특성으로 인해 혼란을 느낀다. 자바스크립트에서는 함수 객체로 많은 것을 할 수 있는데 클래스, 생성자, 메소드도 모두 함수로 구현이 가능하다.

> ECMAScript 6에서 새롭게 클래스가 도입되었다. ES6의 Class는 기존 prototype 기반 객체지향 프로그래밍보다 Class 기반 언어에 익숙한 프로그래머가 보다 빠르게 학습할 수 있는 단순하고 깨끗한 새로운 문법을 제시하고 있다. ES6의 Class가 새로운 객체지향 모델을 제공하는 것이 아니며 Class도 사실 함수이고 기존 prototype 기반 패턴의 Syntactic sugar이다.

# 3. 생성자 함수와 인스턴스의 생성
자바스크립트는 생성자 함수와 new 연산자를 통해 인스턴스를 생성할 수 있다. 이때 생성자 함수는 클래스이자 생성자의 역할을 한다. 

``` javascript
// 생성자 함수(Constructor)
function Person(name) {
  // 프로퍼티
  this.name = name;

  // 메소드
  this.setName = function (name) {
    this.name = name;
  };

  // 메소드
  this.getName = function () {
    return this.name;
  };
}

// 인스턴스의 생성
var me = new Person('Lee');
console.log(me.getName()); // Lee

// 메소드 호출
me.setName('Kim');
console.log(me.getName()); // Kim
```

위 예제는 잘 동작한다. 하지만 이 예제는 문제가 많다. Person 생성자 함수로 여러 개의 인스턴스를 생성해보자.

``` javascript
var me  = new Person('Lee');
var you = new Person('Kim');
var him = new Person('Choi');

console.log(me);  // Person { name: 'Lee', setName: [Function], getName: [Function] }
console.log(you); // Person { name: 'Kim', setName: [Function], getName: [Function] }
console.log(him); // Person { name: 'Choi', setName: [Function], getName: [Function] }
```

위와 같이 인스턴스를 생성하면 각각의 인스턴스에 메소드 setName, getName이 중복되어 생성된다. 즉, 각 인스턴스가 내용이 동일한 메소드를 각자 소유한다. 이는 메모리 낭비인데 생성되는 인스턴스가 많아지거나 메소드가 크거나 많다면 무시할 수 없는 문제이다.

이같은 문제를 해결하려면 다른 접근 방식이 필요한데 그 해답은 프로토타입이다.

# 4. 프로토타입 체이노가 메소드의 정의 

모든 객체는 프로토타입이라는 다른 객체를 가리키는 내부 링크를 가지고 있다. 즉, 프로토타입을 통해 직접 객체를 연결할 수 있는데 이를 프로토타입 체인이라 한다.

프로토타입을 이용하여 생성자 함수 내부의 메소드를 생성자 함수의 prototype 프로퍼티가 가리키는 프로토타입 객체로 이동시키면 생성자 함수에 의해 생성된 모든 인스턴스는 프로토타입 체인을 통해 프로토타입 객체의 메소드를 참조할 수 있다.

``` javascript
function Person(name) {
  this.name = name;
}

// 프로토타입 객체에 메소드 정의
Person.prototype.setName = function (name) {
  this.name = name;
};

// 프로토타입 객체에 메소드 정의
Person.prototype.getName = function () {
  return this.name;
};

var me  = new Person('Lee');
var you = new Person('Kim');
var him = new Person('choi');

console.log(Person.prototype);
// Person { setName: [Function], getName: [Function] }

console.log(me);  // Person { name: 'Lee' }
console.log(you); // Person { name: 'Kim' }
console.log(him); // Person { name: 'choi' }
```

Person 생성자 함수의 prototype 프로퍼티가 가리키는 프로토타입 객체로 이동시킨 setName. getName 메소드는 프로토타입 체인에 의해 모든 인스턴스가 참조할 수 있다. 프로토타입 객체는 상속할 것들이 저장되는 장소이다.

아래는 더글라스 크락포드가 제안한 프로토타입 객체에 메소드를 추가하는 방식이다.

``` javascript
/**
 * 모든 생성자 함수의 프로토타입은 Function.prototype이다. 따라서 모든 생성자 함수는 Function.prototype.method()에 접근할 수 있다.
 * @method Function.prototype.method
 * @param ({string}) (name) - (메소드 이름)
 * @param ({function}) (func) - (추가할 메소드 본체)
 */
Function.prototype.method = function (name, func) {
  // 생성자함수의 프로토타입에 동일한 이름의 메소드가 없으면 생성자함수의 프로토타입에 메소드를 추가
  // this: 생성자함수
  if (!this.prototype[name]) {
    this.prototype[name] = func;
  }
};

/**
 * 생성자 함수
 */
function Person(name) {
  this.name = name;
}

/**
 * 생성자함수 Person의 프로토타입에 메소드 setName을 추가
 */
Person.method('setName', function (name) {
  this.name = name;
});

/**
 * 생성자함수 Person의 프로토타입에 메소드 getName을 추가
 */
Person.method('getName', function () {
  return this.name;
});

var me  = new Person('Lee');
var you = new Person('Kim');
var him = new Person('choi');

console.log(Person.prototype);
// Person { setName: [Function], getName: [Function] }

console.log(me);  // Person { name: 'Lee' }
console.log(you); // Person { name: 'Kim' }
console.log(him); // Person { name: 'choi' }
```