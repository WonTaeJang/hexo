---
title: css3-day-5
date: 2021-04-29 16:38:39
    - css 
    - display
    - visibility
    - opacity
categories: 
    - css
---

## 2.5 CSS3 Display
# display, visibility, opacity 프로퍼티

# 1.display 프로퍼티
display 프로퍼티는 layout 정의에 자주 사용되는 중요한 프로퍼티이다. 

|프로퍼티값 키워드|설명|
|----------------|----|
|block|block 특성을 가지는 요소(block 레벨 요소)로 지정|
|inline|inline 특성을 가지는 요소(inline 레벨 요소)로 지정|
|inline-block|inline-block 특성을 가지는 요소(inline-block 레벨 요소)로 지정|
|none|해당 요소를 화면에 표시하지 않는다(공간조차 사라진다.)|

모든 HTML 요소는 아무런 CSS를 적용하지 않아도 기본적으로 브라우저에 표현되는 디폴트 표시값을 가진다. HTML 요소는 block 또는 inline 튿성을 갖는다. 

아래는 p 요소에 대한 크롬 브라우저의 디폴트 css이다.

``` css
p {
  display: block;
  -webkit-margin-before: 1em;
  -webkit-margin-after: 1em;
  -webkit-margin-start: 0px;
  -webkit-margin-end: 0px;
}
```

> display 프로퍼티는 상속되지 않는다.

## 1.1 block 레벨 요소
block 특성을 가지는 요소(block 레벨 요소 또는 block 요소)는 아래와 같은 특징을 갖는다. 

- 항상 새로운 라인에서 시작한다.
- 화면 크기 전체의 가로폭을 차지한다.(width: 100%)
- width, height, margin, padding 프로퍼티 지정이 가능하다. 
- block 레벨 요소 예
> div
> h1~h6
> p
> ol
> ul
> li
> hr
> table
> form

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    div:nth-of-type(1) {
      background-color: #FFA07A;
      padding: 20px;
    }
    div:nth-of-type(2) {
      background-color: #FF7F50;
      padding: 20px;
      width: 300px;
    }
  </style>
</head>
<body>
  <div>
    <h2>블록 레벨 요소</h2>
    <p>width, height 미지정 → width: 100%; height: auto;</p>
  </div>
  <div>
    <h2>블록 레벨 요소</h2>
    <p>width: 300px → width: 300px; height: auto;</p>
  </div>
</body>
</html>
```
### ***result***

<iframe width='100%' height='350px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    div:nth-of-type(1) {
      background-color: #FFA07A;
      padding: 20px;
    }
    div:nth-of-type(2) {
      background-color: #FF7F50;
      padding: 20px;
      width: 300px;
    }
  </style>
</head>
<body>
  <div>
    <h2>블록 레벨 요소</h2>
    <p>width, height 미지정 → width: 100%; height: auto;</p>
  </div>
  <div>
    <h2>블록 레벨 요소</h2>
    <p>width: 300px → width: 300px; height: auto;</p>
  </div>
</body>
</html>
">
</iframe>

## 1.2 inline 레벨 요소 
inline 특성을 가지는 요소(inline 레벨 요소 또는 inline 요소)는 아래와 같은 특징을 갖는다. 

- 새로운 라인에서 시작하지 않으며 문장의 중간에 들어갈 수 있다. 즉, 줄을 바꾸지 않고 다른 요소와 함께 한 행에 위치한다. 

- content의 너비만큼 가로폭을 차지한다. 

- width, height, margin-top, margin-bottom 프로퍼티를 지정할 수 없다. 상, 하 여백은 line-height로 지정한다. 

- inline 레벨 요소 뒤에 공백(엔터, 스페이스 등)이 있는 경우, 정의하지 않은 space(4px)가 자동 지정된다. 

- inline 레벨 요소 내에 block 레벨 요소를 포함할 수 없다. inline 레벨 요소는 일반적으로 block 레벨 요소에 포함되어 사용된다. 

> - span
> - a
> - strong
> - img
> - input
> - select
> - textarea
> - button

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    span {
      background-color: red;
      color: white;
      padding: 10px;
      /* width, height, margin-top, margin-bottom 프로퍼티를 지정할 수 없다. */
      /* width: 200px; */
      /* margin: 10px; */
      /* 상, 하 여백은 line-height로 지정한다. */
      /* line-height: 50px; */
    }
  </style>
</head>
<body>
  <h1>My <span>Important</span> Heading</h1>
  <span>Inline</span>
  <span>Inline</span><span>Inline</span>
</body>
</html>
```

### ***result***

<iframe width='100%' height='200px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    span {
      background-color: red;
      color: white;
      padding: 10px;
      /* width, height, margin-top, margin-bottom 프로퍼티를 지정할 수 없다. */
      /* width: 200px; */
      /* margin: 10px; */
      /* 상, 하 여백은 line-height로 지정한다. */
      /* line-height: 50px; */
    }
  </style>
</head>
<body>
  <h1>My <span>Important</span> Heading</h1>
  <span>Inline</span>
  <span>Inline</span><span>Inline</span>
</body>
</html>
">
</iframe>

## 1.3 inline-block 레벨 요소
block 과 inline 레벨 요소의 특징을 모두 갖는다. inline 레벨 요소와 같이 한 줄에 표현되면서 width, height, margin 프로퍼티를 모두 지정할 수 있다.
- 기본적으로 inline 레벨요소와 흡사하게 줄을 바꾸지 않고 다른 요소와 함께 한 행에 위치시킬 수 있다. 
- block 레벨 요소처럼 width, height, margin, padding 프로퍼티를 모두 정의할 수 있다. 상,하 여백을 margin과 line-height 두가지 프로퍼티 모두를 통해 제어할 수 있다. 
- content의 너비만큼 가로폭을 차지한다. 
- inline-block 레벨 요소 뒤에 공백(엔터, 스페이스 등)이 있는 경우, 정의하지 않은 space(4px)가 자동 지정된다.

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    .wrapper {
      font-size: 0; /*요소간 간격을 제거*/
    }
    .inline-block {
      display: inline-block;
      vertical-align: middle; /* inline-block 요소 수직 정렬 */
      border: 3px solid #73AD21;
      font-size: 16px;
    }
    .box1 {
      width: 300px;
      height: 70px;
    }
    .box2 {
      width: 300px;
      height: 150px;
    }
  </style>
</head>
<body>
  <div class="inline-block box1">inline-block height 70px</div>
  <div class="inline-block box2">inline-block height 150px</div>

  <div class="wrapper">
    <div class="inline-block box1">inline-block height 70px</div>
    <div class="inline-block box2">inline-block height 150px</div>
  </div>
</body>
</html>
```

### ***result***

<iframe width='100%' height='350px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    .wrapper {
      font-size: 0; /*요소간 간격을 제거*/
    }
    .inline-block {
      display: inline-block;
      vertical-align: middle; /* inline-block 요소 수직 정렬 */
      border: 3px solid #73AD21;
      font-size: 16px;
    }
    .box1 {
      width: 300px;
      height: 70px;
    }
    .box2 {
      width: 300px;
      height: 150px;
    }
  </style>
</head>
<body>
  <div class='inline-block box1'>inline-block height 70px</div>
  <div class='inline-block box2'>inline-block height 150px</div>
  <div class='wrapper'>
    <div class='inline-block box1'>inline-block height 70px</div>
    <div class='inline-block box2'>inline-block height 150px</div>
  </div>
</body>
</html>
">
</iframe>

# 2. visibility 프로퍼티 
visibility 프로퍼티는 요소를 보이게 할 것인지 보이지 않게 할 것인지를 정의한다. 즉, 요소의 렌더링 여부를 결정한다. 

|프러퍼티값 키워드|설명|
|---------------|----|
|visible|해당 요소를 보이게 한다(기본값)|
|hidden|해당 요소를 보이지 않게 한다. display: none; 은 해당 요소의 공간까지 사라지게 하지만 visibility:hidden;은 해당 요소의 공간은 사라지지 않고 남아있게 된다.|
|collapse|table 요소에 사용하며 행이나 열을 보이지 않게 한다.|
|none|table 요소의 row나 column을 보이지 않게 한다. |


``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    .visible { visibility: visible; }
    .hidden  { visibility: hidden; }

    table, td { border: 1px solid black; }
    .collapse { visibility: collapse; }
    /* .collapse { visibility: hidden; } */
  </style>
</head>
<body>
  <h1 class="visible">visibility: visible</h1>
  <h1 class="hidden">visibility: hidden</h1>
  <h1 style="display:none">display:none</h1>

  <table>
    <tr>
      <td>A</td>
      <td>B</td>
    </tr>
    <tr class="collapse">
      <td>C</td>
      <td>D</td>
    </tr>
  </table>
</body>
</html>
```

### ***result***

<iframe width='100%' height='250px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    .visible { visibility: visible; }
    .hidden  { visibility: hidden; }
    table, td { border: 1px solid black; }
    .collapse { visibility: collapse; }
    /* .collapse { visibility: hidden; } */
  </style>
</head>
<body>
  <h1 class='visible'>visibility: visible</h1>
  <h1 class='hidden'>visibility: hidden</h1>
  <h1 style='display:none'>display:none</h1>
  <table>
    <tr>
      <td>A</td>
      <td>B</td>
    </tr>
    <tr class='collapse'>
      <td>C</td>
      <td>D</td>
    </tr>
  </table>
</body>
</html>
">
</iframe>

# 3. opacity 프로퍼티
opacity 프로퍼티는 요소의 투명도를 정의한다. 0.0 ~ 1.0의 값을 입력하며 0.0은 투명, 1.0은 불투명을 의미한다.

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    div, img {
      float: left;
      width: 150px;
      height: 150px;
      margin: 30px;
      background-color: blue;
      color: white;
      opacity: 0.5;
      transition: opacity 1s;
    }
    div:hover, img:hover {
      opacity: 1.0;
    }
  </style>
</head>
<body>
  <div>opacity: 0.5</div>
  <img src="https://poiemaweb.com/img/doug.jpg" alt="doug">
</body>
</html>
```

### ***result***

<iframe width='100%' height='250px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    div, img {
      float: left;
      width: 150px;
      height: 150px;
      margin: 30px;
      background-color: blue;
      color: white;
      opacity: 0.5;
      transition: opacity 1s;
    }
    div:hover, img:hover {
      opacity: 1.0;
    }
  </style>
</head>
<body>
  <div>opacity: 0.5</div>
  <img src='img/cat.png' alt='cat'>
</body>
</html>
">
</iframe>

<br><br>

# Reference
[poiemaweb.com/css3-display](https://poiemaweb.com/css3-display)

[W3C CSS Document](https://www.w3.org/TR/CSS/)

