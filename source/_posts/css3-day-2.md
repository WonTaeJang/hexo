---
title: css3-day-2
date: 2021-04-22 17:21:37
    - css 
    - Selector
categories: 
    - css
---

## CSS3 Selector
# Selector
CSS(Cascading Style Sheets)는 HTML 요소(Element)의 style(design, layout etc)을 정의한다. 그리하려면 HTML이 존재하여야 하고 또한 style을 적용하고자하는 HTML 요소를 특정할 필요가 있다. 

이러한 목적으로 사용되는 것이 셀렉터(Selector)이다. 즉, style을 적용하고자 하는 HTML 요소를 셀렉터로 특정하고 선택된 요소에 스타일을 정의하는 것이다.

 ![CSS Rule Set](img/selector.gif)

 ``` html
 <!DOCTYPE html>
<html>
<head>
  <style>
    h1 { color: red; }
    p  { color: blue; }
  </style>
</head>
<body>
  <h1>Hello World!</h1>
  <p>This paragraph is styled with CSS.</p>
</body>
</html>
 ```

<!DOCTYPE html>
<html>
<body>
  <h1 style="color: red;">Hello World!</h1>
  <p style="color: blue;">This paragraph is styled with CSS.</p>
</body>
</html>

복수개의 셀렉터를 연속하여 지정할 수 있으며 쉼표(,)로 구분한다.

``` css
h1, p { color: red; }
```

# 1. 전체 셀렉터 (Universal Selector)

|패턴|Description|
|-----|-----------|
|*|HTML 문서 내의 모든 요소를 선택한다. html 요소를 포함한 모든 요소가 선택된다. (head 요소도 포함된다)|

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* 모든 요소를 선택 */
    * { color: red; }
  </style>
</head>
<body>
  <h1>Heading</h1>
  <div>
    <p>paragraph 1</p>
    <p>paragraph 2</p>
  </div>
  <p>paragraph 3</p>
</body>
</html>
```
### ***result***

<iframe srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    * { color: red; }
  </style>
</head>
<body>
  <h1>Heading</h1>
  <div>
    <p>paragraph 1</p>
    <p>paragraph 2</p>
  </div>
  <p>paragraph 3</p>
</body>
</html>">
</iframe>

# 2. 태그 셀렉터 (Type Selector)

|패턴|Description|
|-----|-----------|
|태그명|지정된 태그명을 가지는 요소를 선택한다.|

지정된 태그명을 가지는 요소를 선택한다. 

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* 모든 p 태그 요소를 선택 */
    p { color: red; }
  </style>
</head>
<body>
  <h1>Heading</h1>
  <div>
    <p>paragraph 1</p>
    <p>paragraph 2</p>
  </div>
  <p>paragraph 3</p>
</body>
</html>
```

### ***result***

<iframe srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    /* 모든 p 태그 요소를 선택 */
    p { color: red; }
  </style>
</head>
<body>
  <h1>Heading</h1>
  <div>
    <p>paragraph 1</p>
    <p>paragraph 2</p>
  </div>
  <p>paragraph 3</p>
</body>
</html>">
</iframe>

# 3. ID 셀렉터 (ID Selector)

|패턴|Description|
|-----|-----------|
|#id 어트리뷰트 값|id 어프리뷰트 값을 지정하여 일치하는 요소를 선택한다. id 어트리뷰트 값은 중복될 수 없는 유일한 값이다.|

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* id 어트리뷰트 값이 p1인 요소를 선택 */
    #p1 { color: red; }
  </style>
</head>
<body>
  <h1>Heading</h1>
  <div class="container">
    <p id="p1">paragraph 1</p>
    <p id="p2">paragraph 2</p>
  </div>
  <p>paragraph 3</p>
</body>
</html>
```

### ***result***

<iframe srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    /* id 어트리뷰트 값이 p1인 요소를 선택 */
    #p1 { color: red; }
  </style>
</head>
<body>
  <h1>Heading</h1>
  <div class='container'>
    <p id='p1'>paragraph 1</p>
    <p id='p2'>paragraph 2</p>
  </div>
  <p>paragraph 3</p>
</body>
</html>">
</iframe>

# 4. 클래스 셀렉터 (Class Selector)

|패턴|Description|
|-----|-----------|
|.class 어트리뷰트 값|class 어트리뷰트 값을 지정하여 일치하는 요소를 선택한다. class 어트리뷰트 값은 중복될 수 있다.|

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* class 어트리뷰트 값이 container인 모든 요소를 선택 */
    /* color 어트리뷰트는 자식 요소에 상속된다. */
    .container { color: red; }
    /* not supported in IE */
    #p2 { color: initial; }
  </style>
</head>
<body>
  <h1>Heading</h1>
  <div class="container">
    <p id="p1">paragraph 1</p>
    <p id="p2">paragraph 2</p>
  </div>
  <p>paragraph 3</p>
</body>
</html>
```

### ***result***

<iframe srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    /* class 어트리뷰트 값이 container인 모든 요소를 선택 */
    /* color 어트리뷰트는 자식 요소에 상속된다. */
    .container { color: red; }
    /* not supported in IE */
    #p2 { color: initial; }
  </style>
</head>
<body>
  <h1>Heading</h1>
  <div class='container'>
    <p id='p1'>paragraph 1</p>
    <p id='p2'>paragraph 2</p>
  </div>
  <p>paragraph 3</p>
</body>
</html>">
</iframe>

HTML 요소에 class 어트리뷰트 값은 공백으로 구분하여 여러 개 지정할 수 있다. 아래와 같이 클래스 셀렉터를 사용하여 미리 스타일을 정의해 두고, HTML 요소는 이미 정의되어 있는 클래스를 지정하는 것으로 필요한 스타일을 지정할 수 있다. 이것은 **재사용**의 측면에서 유용하다.

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* class 어트리뷰트 값이 text-center인 모든 요소를 선택 */
    .text-center { text-align: center; }
    /* class 어트리뷰트 값이 text-large인 모든 요소를 선택 */
    .text-large  { font-size: 200%; }
    /* class 어트리뷰트 값이 text-red인 모든 요소를 선택 */
    .text-red    { color: red; }
    /* class 어트리뷰트 값이 text-blue인 모든 요소를 선택 */
    .text-blue   { color: blue; }
  </style>
</head>
<body>
  <p class="text-center">Center</p>
  <p class="text-large text-red">Large Red</p>
  <p class="text-center text-large text-blue">Center Large Blue</p>
</body>
</html>
```

### ***result***

<iframe srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    /* class 어트리뷰트 값이 text-center인 모든 요소를 선택 */
    .text-center { text-align: center; }
    /* class 어트리뷰트 값이 text-large인 모든 요소를 선택 */
    .text-large  { font-size: 200%; }
    /* class 어트리뷰트 값이 text-red인 모든 요소를 선택 */
    .text-red    { color: red; }
    /* class 어트리뷰트 값이 text-blue인 모든 요소를 선택 */
    .text-blue   { color: blue; }
  </style>
</head>
<body>
  <p class='text-center'>Center</p>
  <p class='text-large text-red'>Large Red</p>
  <p class='text-center text-large text-blue'>Center Large Blue</p>
</body>
</html>">
</iframe>

# 5. 어트리뷰트 셀렉터 (Attribute Selector)

|패턴|Description|
|-----|-----------|
|셀렉터[어트리뷰트]|지정된 어트리뷰트를 갖는 모든 요소를 선택한다.|

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* a 요소 중에 href 어트리뷰트를 갖는 모든 요소 */
    a[href] { color: red; }
  </style>
</head>
<body>
  <a href="http://www.poiemaweb.com">poiemaweb.com</a><br>
  <a href="http://www.google.com" target="_blank">google.com</a><br>
  <a href="http://www.naver.com" target="_top">naver.com</a>
</body>
</html>
```

### ***result***

<iframe srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    /* a 요소 중에 href 어트리뷰트를 갖는 모든 요소 */
    a[href] { color: red; }
  </style>
</head>
<body>
  <a href='https://wontaejang.github.io/'>wontaejang.github.io</a><br>
  <a href='http://www.google.com' target='_blank'>google.com</a><br>
  <a href='http://www.naver.com' target='_top'>naver.com</a>
</body>
</html>">
</iframe>

|패턴|Description|
|-----|-----------|
|셀렉터[어트리뷰트="값"]|지정된 어트리뷰트를 가지며 지정된 값과 어트리뷰트의 값이 일치하는 모든 요소를 선택한다.|

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* a 요소 중에 target 어트리뷰트의 값이 "_blank"인 모든 요소 */
    a[target="_blank"] { color: red; }
  </style>
</head>
<body>
  <a href="https://wontaejang.github.io">wontaejang.github.io</a><br>
  <a href="http://www.google.com" target="_blank">google.com</a><br>
  <a href="http://www.naver.com" target="_top">naver.com</a>
</body>
</html>
```

### ***result***

<iframe srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    /* a 요소 중에 target 어트리뷰트의 값이 '_blank'인 모든 요소 */
    a[target='_blank'] { color: red; }
  </style>
</head>
<body>
  <a href='https://wontaejang.github.io'>wontaejang.github.io</a><br>
  <a href='http://www.google.com' target='_blank'>google.com</a><br>
  <a href='http://www.naver.com' target='_top'>naver.com</a>
</body>
</html>">
</iframe>

|패턴|Description|
|-----|-----------|
|셀렉터[어트리뷰트~="값"]|지정된 어트리뷰트의 값이 지정된 값을 (공백으로 분리된) 단어로 포함하는 요소를 선택한다.|

``` html 
<!DOCTYPE html>
<html>
<head>
  <style>
    /* h1 요소 중에 title 어트리뷰트 값에 "first"를 단어로 포함하는 요소 */
    h1[title~="first"] { color: red; }
  </style>
</head>
<body>
  <h1 title="heading first">Heading first</h1>
  <h1 title="heading-first">Heading-first</h1>
  <h1 title="heading second">Heading second</h1>
  <h1 title="heading third">Heading third</h1>
</body>
</html>
```

### ***result***

<iframe width='100%' height='300px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    /* h1 요소 중에 title 어트리뷰트 값에 'first'를 단어로 포함하는 요소 */
    h1[title~='first'] { color: red; }
  </style>
</head>
<body>
  <h1 title='heading first'>Heading first</h1>
  <h1 title='heading-first'>Heading-first</h1>
  <h1 title='heading second'>Heading second</h1>
  <h1 title='heading third'>Heading third</h1>
</body>
</html>
">
</iframe>

|패턴|Description|
|-----|-----------|
|셀렉터[어트리뷰트|="값"]|지정된 어트리뷰트의 값과 일치하거나 지정 어트리뷰트 값 뒤 연이은 하이픈("값-")으로 시작하는 요소를 선택한다.|

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* p 요소 중에 lang 어트리뷰트 값이 "en"과 일치하거나 "en-"로 시작하는 요소 */
    p[lang|="en"] { color: red; }
  </style>
</head>
<body>
  <p lang="en">Hello!</p>
  <p lang="en-us">Hi!</p>
  <p lang="en-gb">Ello!</p>
  <p lang="us">Hi!</p>
  <p lang="no">Hei!</p>
</body>
</html>
```

### ***result***

<iframe width='100%' height='200px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    /* p 요소 중에 lang 어트리뷰트 값이 'en'과 일치하거나 'en-'로 시작하는 요소 */
    p[lang|='en'] { color: red; }
  </style>
</head>
<body>
  <p lang='en'>Hello!</p>
  <p lang='en-us'>Hi!</p>
  <p lang='en-gb'>Ello!</p>
  <p lang='us'>Hi!</p>
  <p lang='no'>Hei!</p>
</body>
</html>
">
</iframe>

|패턴|Description|
|-----|-----------|
|셀렉터[어트리뷰트^="값"]|지정된 어트리뷰트 값으로 시작하는 요소를 선택한다.|

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* a 요소 중에 href 어트리뷰트 값이 "https://"로 시작하는 요소 */
    a[href^="https://"] { color: red; }
  </style>
</head>
<body>
  <a href="https://www.test.com">https://www.test.com</a><br>
  <a href="http://www.test.com">http://www.test.com</a>
</body>
</html>
```

### ***result***

<iframe width='100%' height='100px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    /* a 요소 중에 href 어트리뷰트 값이 'https://'로 시작하는 요소 */
    a[href^='https://'] { color: red; }
  </style>
</head>
<body>
  <a href='https://www.test.com'>https://www.test.com</a><br>
  <a href='http://www.test.com'>http://www.test.com</a>
</body>
</html>
">
</iframe>

|패턴|Description|
|-----|-----------|
|셀렉터[어트리뷰트$="값"]|지정된 어트리뷰트 값으로 끝나는 요소를 선택한다.|

### ***result***

<iframe width='100%' height='100px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    /* a 요소 중에 href 어트리뷰트 값이 '.html'로 끝나는 요소 */
    a[href$='.html'] { color: red; }
  </style>
</head>
<body>
  <a href='test.html'>test.html</a><br>
  <a href='test.jsp'>test.jsp</a>
</body>
</html>
">
</iframe>

|패턴|Description|
|-----|-----------|
|셀렉터[어트리뷰트*="값"]|지정된 어트리뷰트 값을 포함하는 요소를 선택한다.|

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    /* div 요소 중에서 class 어트리뷰트 값에 "test"를 포함하는 요소 */
    div[class*="test"] { color: red; }
    /* div 요소 중에서 class 어트리뷰트 값에 "test"를 단어로 포함하는 요소 */
    div[class~="test"] { background-color: yellow; }
  </style>
</head>
<body>
  <div class="first_test">The first div element.</div>
  <div class="second">The second div element.</div>
  <div class="test">The third div element.</div>
  <p class="test">This is some text in a paragraph.</p>
</body>
</html>
```

### ***result***

<iframe width='100%' height='200px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    /* div 요소 중에서 class 어트리뷰트 값에 'test'를 포함하는 요소 */
    div[class*='test'] { color: red; }
    /* div 요소 중에서 class 어트리뷰트 값에 'test'를 단어로 포함하는 요소 */
    div[class~='test'] { background-color: yellow; }
  </style>
</head>
<body>
  <div class='first_test'>The first div element.</div>
  <div class='second'>The second div element.</div>
  <div class='test'>The third div element.</div>
  <p class='est'>This is some text in a paragraph.</p>
</body>
</html>
">
</iframe>



[참조 사이트: https://poiemaweb.com/css3-selector](https://poiemaweb.com/css3-selector)