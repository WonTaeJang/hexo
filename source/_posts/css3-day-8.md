---
title: css3-day-8
date: 2021-05-05 23:06:32
    - css 
    - position
categories: 
    - css
---

### 2.8 CSS3 Position
# 요소의 위치 정의

<br><br>

# 1. postion 프로퍼티
position 프로퍼티는 요소의 위치를 정의한다. top, bottom, left, right 프로퍼티와 함께 사용하여 위치를 지정한다.

## 1.1 static (기본 위치)
static은 position 프로퍼티의 기본값으로 position 프로퍼티를 지정하지 않았을 때와 같다. 

기본적인 요소의 배치 순서에 따라 위에서 아래로, 왼쪽ㅇ에서 오른족으로 순서에 따라 배치되며 부요 요소 내에 자식 요소로서 존재할 때는 부모 요소의 위치를 기준으로 배치된다. 

기본적으로 이 값을 지정할 일은 없지만 이미 설정된 position을 무력화하기 위해 사용될 수 있다. 

좌표 프로퍼티(top, bottom, left, right)를 같이 사용할 수 없으며 사용할 경우에는 무시 된다.

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    body { margin: 0; }
    .parent {
      width: 150px;
      height: 150px;
      background: #bcbcbc;
      border: 1px solid #bcbcbc;
    }
    .static-box {
      position: static;
      background: #2E303D;
      color: #e55c3c;
      font-weight: bold;
      text-align: center;
      line-height: 150px;
    }
  </style>
</head>
<body>
  <div class="parent">
    <div class="static-box">static box</div>
  </div>
</body>
</html>
```
### ***result***

<iframe width='100%' height='200px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    body { margin: 0; }
    .parent {
      width: 150px;
      height: 150px;
      background: #bcbcbc;
      border: 1px solid #bcbcbc;
    }
    .static-box {
      position: static;
      background: #2E303D;
      color: #e55c3c;
      font-weight: bold;
      text-align: center;
      line-height: 150px;
    }
  </style>
</head>
<body>
  <div class='parent'>
    <div class='static-box'>static box</div>
  </div>
</body>
</html>
">
</iframe>

## 1.2 relative(상대위치)
기본 위치(static으로 지정되었을 때의 위치)를 기준으로 좌표 프로퍼티(top, bottom, left, right)를 사용하여 위치를 이동시킨다. static을 선언한 요소와 relative를 선언한 요소의 차이점은 좌표 프로퍼티의 동작 여부뿐이며 그외는 동일하게 동작한다. 

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    body { margin: 0; }
    .parent {
      width: 150px;
      height: 150px;
      background: #bcbcbc;
      border: 1px solid #bcbcbc;
      margin: 50px;
    }
    .relative-box {
      position: relative;
      top: 50px; left: 50px;
      background: #2E303D;
      color: #e55c3c;
      font-weight: bold;
      text-align: center;
      line-height: 150px;
    }
  </style>
</head>
<body>
  <div class="parent">
    <div class="relative-box">relative box</div>
  </div>
</body>
</html>
```
### ***result***

<iframe width='100%' height='300px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    body { margin: 0; }
    .parent {
      width: 150px;
      height: 150px;
      background: #bcbcbc;
      border: 1px solid #bcbcbc;
      margin: 50px;
    }
    .relative-box {
      position: relative;
      top: 50px; left: 50px;
      background: #2E303D;
      color: #e55c3c;
      font-weight: bold;
      text-align: center;
      line-height: 150px;
    }
  </style>
</head>
<body>
  <div class='parent'>
    <div class='relative-box'>relative box</div>
  </div>
</body>
</html>
">
</iframe>

위 예제를 보면 parent 클래스의 자식인 relative-box 클래스 요소의 width, height가 부모 요소와 동일하다. 이는 상속에 의한 것이 아니라(width, height는 상속되지 않는다.) relative를 적용한 요소는 좌표 프로퍼티가 적용되는 것만 다를 뿐 그 이외는 static을 지정했을 때와 동일하게 동작하기 때문이다. 즉, width는 100%가 적용되어 부모 요소의 width와 동일한 값을 갖게 된 것이고, height는 auto가 적용되지만 line-height: 150px이 적용되어 부모 요소와 hight가 동일하게 된 것이다.


``` html

```
### ***result***

<iframe width='100%' height='200px' srcdoc="

">
</iframe>