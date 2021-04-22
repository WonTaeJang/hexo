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

[참조 사이트: https://poiemaweb.com/css3-selector](https://poiemaweb.com/css3-selector)