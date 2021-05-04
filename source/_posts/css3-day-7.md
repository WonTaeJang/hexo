---
title: css3-day-7
date: 2021-05-04 23:13:00
    - css 
    - font
    - text
categories: 
    - css
---

## 2.7 CSS3 Font & Text
# 폰트와 텍스트

폰트 및 텍스트 관련 프로퍼티는 폰트의 크기, 폰트의 지정, 폰트의 스타일, 텍스트 정렬 등을 정의한다. 

# 1. font-size 프로퍼티
텍스트의 크기를 정의한다. 

- [font-size](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size)

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    .font-size-40 { font-size: 40px; }
    .font-size-2x { font-size: 2.0em; }
    .font-size-150ps { font-size: 150%; }
    .font-size-large { font-size: large; }
  </style>
</head>
<body>
  <p>default font size: 16px</p>
  <p class='font-size-40'>font-size: 40px</p>
  <p class='font-size-2x'>font-size: 2.0em</p>
  <p class='font-size-150ps'>font-size: 150%</p>
  <p class='font-size-large'>font-size: large</p>
</body>
</html>
```
### ***result***

<iframe width='100%' height='400px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    .font-size-40 { font-size: 40px; }
    .font-size-2x { font-size: 2.0em; }
    .font-size-150ps { font-size: 150%; }
    .font-size-large { font-size: large; }
  </style>
</head>
<body>
  <p>default font size: 16px</p>
  <p class='font-size-40'>font-size: 40px</p>
  <p class='font-size-2x'>font-size: 2.0em</p>
  <p class='font-size-150ps'>font-size: 150%</p>
  <p class='font-size-large'>font-size: large</p>
</body>
</html>
">
</iframe>

# 2. font-family 프로퍼티
폰트를 지정한다. 컴퓨터에 해당 폰트가 설치되어 있지 않으면 적용되지 않는다. 

- [font-family](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)

폰트는 여러 개를 동시에 지정이 가능하다. 첫번째 지정한 폰트가 클라이언트 컴퓨터에 설치되어 있지 않은 경우, 다음에 지정된 폰트를 적용한다. 따라서 마지막에 지정하는 폰트는 대부분의 OS에 기본적으로 설치되어 있는 generic-family 폰트(Serif, Sans-serif, Mono spase)를 지정하는 것이 일반적이다. 

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    .serif {
      font-family: "Times New Roman", Times, serif;
    }

    .sans-serif {
      font-family: Arial, Helvetica, sans-serif;
    }

    .monospace {
      font-family: "Courier New", Courier, monospace;
    }
  </style>
</head>
<body>
  <h1>font-family</h1>
  <p class="serif">Times New Roman font.</p>
  <p class="sans-serif">Arial font.</p>
  <p class="monospace">Courier New font.</p>
</body>
</html>
```
### ***result***

<iframe width='100%' height='200px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    .serif {
      font-family: 'Times New Roman', Times, serif;
    }
    .sans-serif {
      font-family: Arial, Helvetica, sans-serif;
    }
    .monospace {
      font-family: 'Courier New', Courier, monospace;
    }
  </style>
</head>
<body>
  <h1>font-family</h1>
  <p class='serif'>Times New Roman font.</p>
  <p class='sans-serif'>Arial font.</p>
  <p class='monospace'>Courier New font.</p>
</body>
</html>
">
</iframe>

# 3. font-style / font-weight 프로퍼티

font-style 프로퍼티는 이탤릭체의 지정, font-weight 프로퍼티는 폰트 굵기 지정에 사용된다. 

- [font-style](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)

- [font-weight](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    p { font-size: 2.0em; }

    /*
      font-style
      normal / italic / oblique
    */
    .italic {
      font-style: italic;
    }

    /*
      font-weight
      100 ~ 900 or normal / bold / lighter / bolder
    */
    .light {
      font-weight: lighter;
    }
    .thick {
      font-weight: bold;
    }
    .thicker {
      font-weight: 900;
    }
  </style>
</head>
<body>
  <p>normal style.</p>
  <p class="italic">font-style: italic</p>

  <p class="light">font-weight: lighter</p>
  <p class="thick">font-weight: bold</p>
  <p class="thicker">font-weight: 900</p>
</body>
</html>
```
### ***result***

<iframe width='100%' height='480px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    p { font-size: 2.0em; }
    /*
      font-style
      normal / italic / oblique
    */
    .italic {
      font-style: italic;
    }
    /*
      font-weight
      100 ~ 900 or normal / bold / lighter / bolder
    */
    .light {
      font-weight: lighter;
    }
    .thick {
      font-weight: bold;
    }
    .thicker {
      font-weight: 900;
    }
  </style>
</head>
<body>
  <p>normal style.</p>
  <p class='italic'>font-style: italic</p>
  <p class='light'>font-weight: lighter</p>
  <p class='thick'>font-weight: bold</p>
  <p class='thicker'>font-weight: 900</p>
</body>
</html>
">
</iframe>

# 4. font Shorthand
Shorthand Syntax

``` code
font : font-style(optional) font-variant(optional) font-weight(optional) font-size(mandatory) line-height(optional) font-family(mandatory)
```

``` css
/* size | family */
font: 2em "Open Sans", serif;

/* style | size | family */
font: italic 2em "Open Sans", sans-serif;

/* style | variant | weight | size/line-height | family */
font: italic small-caps bolder 16px/1.2 monospace;

/* style | variant | weight | size/line-height | family */
/* font-variant: small-caps; 소문자를 대문자로 만든다. 단 크기는 일반 대문자에 비해 더 작다.*/
font: italic small-caps bolder 16px/3 cursive;
```

# 5. line-height 프로퍼티
텍스트의 높이를 지정한다. 텍스트 수직 정렬에도 응용되어 사용된다.
- [line-height](https://developer.mozilla.org/ko/docs/Web/CSS/line-height)

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    .small {
      line-height: 70%; /* 16px * 70% */
    }
    .big {
      line-height: 1.2; /* 16px * 1.2 */
    }
    .lh-3x {
      line-height: 3.0; /* 16px * 3 */
    }

  </style>
</head>
<body>
  <p>
    default line-height.<br>
    default line-height.<br>
    대부분 브라우저의 default line height는 약 110% ~ 120%.<br>
  </p>

  <p class="small">
    line-height: 70%<br>
    line-height: 70%<br>
  </p>

  <p class="big">
    line-height: 1.2<br>
    line-height: 1.2<br>
  </p>

  <p class="lh-3x">
    line-height: 3.0<br>
    line-height: 3.0<br>
  </p>
</body>
</html>
```
### ***result***

<iframe width='100%' height='300px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    .small {
      line-height: 70%; /* 16px * 70% */
    }
    .big {
      line-height: 1.2; /* 16px * 1.2 */
    }
    .lh-3x {
      line-height: 3.0; /* 16px * 3 */
    }
  </style>
</head>
<body>
  <p>
    default line-height.<br>
    default line-height.<br>
    대부분 브라우저의 default line height는 약 110% ~ 120%.<br>
  </p>
  <p class='small'>
    line-height: 70%<br>
    line-height: 70%<br>
  </p>
  <p class='big'>
    line-height: 1.2<br>
    line-height: 1.2<br>
  </p>
  <p class='lh-3x'>
    line-height: 3.0<br>
    line-height: 3.0<br>
  </p>
</body>
</html>
">
</iframe>

다음은 수직 중앙 정렬 예제이다. a 요소의 line-height 값과 a 요소를 감싸는 div 요소의 height 값을 일치시킨다.

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    .button {
      width: 150px;
      height: 70px;
      background-color: #FF6A00;
      border-radius: 30px;
      box-shadow: 5px 5px 5px #A9A9A9;
    }
    .button > a {
      display: block;
      font: italic bold 2em/70px Arial, Helvetica, sans-serif;
      text-decoration: none;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="button">
    <a href="#">Click</a>
  </div>
</body>
</html>
```
### ***result***

<iframe width='100%' height='100px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    .button {
      width: 150px;
      height: 70px;
      background-color: #FF6A00;
      border-radius: 30px;
      box-shadow: 5px 5px 5px #A9A9A9;
    }
    .button > a {
      display: block;
      font: italic bold 2em/70px Arial, Helvetica, sans-serif;
      text-decoration: none;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class='button'>
    <a href='#'>Click</a>
  </div>
</body>
</html>
">
</iframe>

# 6. letter-spacing 프로퍼티
글자 사이의 간격을 지정한다. 

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    .loose {
      letter-spacing: 2px;
    }
    .tight {
      letter-spacing: -1px;
    }
  </style>
</head>
<body>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit</p>

  <p class="loose">Lorem ipsum dolor sit amet, consectetur adipisicing elit</p>

  <p class="tight">Lorem ipsum dolor sit amet, consectetur adipisicing elit</p>
</body>
</html>
```
### ***result***

<iframe width='100%' height='200px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    .loose {
      letter-spacing: 2px;
    }
    .tight {
      letter-spacing: -1px;
    }
  </style>
</head>
<body>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit</p>
  <p class='loose'>Lorem ipsum dolor sit amet, consectetur adipisicing elit</p>
  <p class='tight'>Lorem ipsum dolor sit amet, consectetur adipisicing elit</p>
</body>
</html>
">
</iframe>

# 7. text-align 프로퍼티
텍스트의 수평 정렬을 정의한다. 

``` css
    h1 { text-align: center; }
    h3 { text-align: right; }
    p.left  { text-align: left; }
    p.justify  { text-align: justify; }
    a  { text-align: center; }
```

# 8. text-decoration 프로퍼티 
text-decoration 프로퍼티를 사용하여 링크 underline 을 제거할 수 있다. 또는 텍스트에 underline, overline, line-through를 추가할 수 있다.

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    a { text-decoration: none; }

    p:nth-of-type(1) { text-decoration: overline; }
    p:nth-of-type(2) { text-decoration: line-through; }
    p:nth-of-type(3) { text-decoration: underline; }
  </style>
</head>
<body>
  <a href='#'>text-decoration: none</a>

  <p>text-decoration: overline</p>
  <p>text-decoration: line-through</p>
  <p>text-decoration: underline</p>
</body>
</html>
```
### ***result***

<iframe width='100%' height='150px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    a { text-decoration: none; }
    p:nth-of-type(1) { text-decoration: overline; }
    p:nth-of-type(2) { text-decoration: line-through; }
    p:nth-of-type(3) { text-decoration: underline; }
  </style>
</head>
<body>
  <a href='#'>text-decoration: none</a>
  <p>text-decoration: overline</p>
  <p>text-decoration: line-through</p>
  <p>text-decoration: underline</p>
</body>
</html>
">
</iframe>

# 9. white-space 프로퍼티
white space는 공백(space), 들여쓰기(tab), 줄바꿈(line break)을 의미한다. html은 기본적으로 연속된 공백(space), 들여쓰기(tab)는 1번만 실행되며 줄바꿈(line break)은 무시된다. 또한 텍스트는 부모의 가로 영역을 벗어나지 않고 자동 줄바꿈(wrap)된다. white-space 프로퍼티는 이러한 기본 동작을 제어하기 위한 프로퍼티이다. 

|프로퍼티값|line break|space/tab|wrapping(자동줄바꿈)|
|---------|----------|---------|-------------------|
|normal|무시|1번만 반영|O|
|nowrap|무시|1번만 반영|X|
|pre|반영|그래도 반영|X|
|pre-wrap|반영|그래로 반영|O|
|pre-line|반영|1번만 반영|O|

``` css
    .normal { white-space: normal; }
    .nowrap { white-space: nowrap; }
    .pre    { white-space: pre; }
    .pre-wrap { white-space: pre-wrap; }
    .pre-line { white-space: pre-line; }
```

# 10. text-overflow 프로퍼티
부모 영역을 벗어난 wrapping(자동줄바꿈)이 되지 않은 텍스트의 처리 방법을 정의한다. 이 프로퍼티를 사용하기 위해서는 아래의 조건이 필요하다. 

- width 프로퍼티가 지정되어 있어야 한다. 이를 위해 필요할 경우 block 레벨 요소로 변경하여야 한다. 

- 자동 줄바꿈을 방지하려면 white-space 프로퍼티를 nowrap으로 설정한다. 

- overflow 프로퍼티에 반드시 "visible"이외의 값이 지정되어 이어야 한다. 

``` css
/* 부모 영역을 벗어난 텍스트를 잘라내어 보이지 않게 하고 말줄임표(...)를 표시한다. */
.truncate {
  width: 150px;             /* width가 지정되어 있어야 한다. */
  white-space: nowrap;      /* 자동 줄바꿈을 방지 */
  overflow: hidden;         /* 반드시 "visible" 이외의 값이 지정되어 있어야 한다. */
  text-overflow: ellipsis;  /* ellipsis or clip */
}
```

text-overflow 프로퍼티에 설정할 수 있는 프로퍼티 값은 아래와 같다. 

|프로퍼티값|Description|  |
|---------|-----------|--|
|clip|영역을 벗어난 텍스트를 표시하지 않는다. (default)||
|ellipsis|영역을 벗어난 텍스트를 잘라내어 보이지 않게 하고 말줄임표(...)를 표시한다.||
|<!-|< string > |프로퍼티값으로 지정한 임의의 문자열을 출력한다. |

``` html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <style>
    div {
      width: 150px; /* width가 지정되어 있어야 한다. */
      height: 150px;
      padding: 10px;
      margin: 40px;
      border-radius: 6px;
      border-color: gray;
      border-style: dotted;
      white-space: nowrap; /* 자동 줄바꿈을 방지 */
      overflow: hidden;    /* 반드시 "visible" 이외의 값이 지정되어 있어야 한다. */
    }
    .clip     { text-overflow: clip; }
    .ellipsis { text-overflow: ellipsis; }
  </style>
</head>
<body>
  <h1>text-overflow</h1>
  <div class="clip">
    <h3>clip</h3>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit
  </div>
  <div class="ellipsis">
    <h3>ellipsis</h3>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit
  </div>
</body>
</html>
```
### ***result***

<iframe width='100%' height='500px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <meta charset='utf-8'>
  <style>
    div {
      width: 150px; /* width가 지정되어 있어야 한다. */
      height: 150px;
      padding: 10px;
      margin: 40px;
      border-radius: 6px;
      border-color: gray;
      border-style: dotted;
      white-space: nowrap; /* 자동 줄바꿈을 방지 */
      overflow: hidden;    /* 반드시 'visible' 이외의 값이 지정되어 있어야 한다. */
    }
    .clip     { text-overflow: clip; }
    .ellipsis { text-overflow: ellipsis; }
  </style>
</head>
<body>
  <h1>text-overflow</h1>
  <div class='clip'>
    <h3>clip</h3>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit
  </div>
  <div class='ellipsis'>
    <h3>ellipsis</h3>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit
  </div>
</body>
</html>
">
</iframe>

# 11. word-wrap 프로퍼티
한 단어의 길이가 길어서 부모 영역을 벗어난 텍스트의 처리 방법을 정의한다. link 등을 표기할 때 그 길이가 매우 길어지는데 이 프로퍼티를 사용하지 않으면 부모 영역을 넘어가게 된다.

``` css
 .word-wrap { word-wrap: break-word; }
```

# 12. word-break 프로퍼티
한 단어의 길이가 길어서 부모 영역을 벗어난 텍스트의 처리 방법을 정의한다. 

word-wrap 프로퍼티는 단어를 어느 정도는 고려한다. word-break: break-all; 는 단어를 고려하지 않고 부모 영역에 맞추어 강제 개행한다. 

<br><br>

# Reference
[poiemaweb.com/css3-font-text](https://poiemaweb.com/css3-font-text)

[W3C CSS Document](https://www.w3.org/TR/CSS/)


