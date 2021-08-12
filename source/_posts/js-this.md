---
title: js-this
date: 2021-08-12 11:01:30
    - javascript 
    - this
categories: 
    - javascript
---

# 함수 호출 방식에 의해 결정되는 this
자바스크립트의 함수는 호출될 때, 매개변수로 전달 되는 인자값 이외에, arguments 객체와 this를 암묵적으로 전달 받는다. 

``` javascript
function square(number) {

  console.log(arguments);
  console.log(this);

  return number * number;
}

square(2);
```

자바스크립트의 this keyword는 Java와 같은익숙한 언어의 개념과 달라 개발자에게 혼란을 준다. 

Java에서의 this는 인스턴스 자신(self)을 가리키는 참조변수이다. this가 객체 자신에 대한 참조 값을 가지고 있다는 뜻이다. 주로 매개변수와 객체 자신이 가지고 있는 멤버변수명이 같을 경우 이를 구분하기 위해서는 사용된다. 아래 Java 코드의 생성자 함수 내의 this.name은 멤버변수를 의미하며 name은 생성자 함수가 전달받은 매개변수를 의미한다. 

``` java
public Class Person {

  private String name;

  public Person(String name) {
    this.name = name;
  }
}
```

