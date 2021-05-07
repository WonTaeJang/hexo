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

1.3 absolute (절대위치)
부모 요소 또는 가장 가까이 있는 조상 요소(static 제외)를 기준으로 좌표 프로퍼티(top, bottom, left, right)만큼 이동한다. 즉, relative, absolute, fixed 프로퍼티가 선언되어 있는 부모 또는 조상 요소를 기준으로 위치가 결정된다. 

만일 부모 또는 조상 요소가 static인 경우, dovument body를 기준으로 하여 좌표 프로퍼티대로 위치하게 된다. 

따라서 부모 요소를 배치의 기준으로 삼기 위해서는 부모 요소에 relative를 정의하여야 한다.

이때 다른 요소가 먼저 위치를 점유하고 있어도 뒤로 밀리지 않고 덮어쓰게 된다. (이런 특성을 부유 또는 부유 객체라 한다.)

absolute 선언 시, block 레벨 요소의 width는 inline 요소와 같이 content에 맞게 변화되므로 적절한 width를 지정하여야 한다.

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    body { margin: 0; }
    .parent {
      width: 200px;
      height: 200px;
      background: #bcbcbc;
      border: 1px solid #bcbcbc;
      margin: 50px 0 0 300px;
      position: relative;
    }
    .absolute-box {
      position: absolute;
      height: 200px; width: 200px;
      top: 50px; left: 50px;
      color: #e55c3c;
      font-weight: bold;
      text-align: center;
      background: #2E303D;
      line-height: 200px;
    }
  </style>
</head>
<body>
  <div class="parent">
    <div class="absolute-box">absolute box (in parent)</div>
  </div>
  <div class="absolute-box">absolute box (no parent)</div></body>
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
      width: 200px;
      height: 200px;
      background: #bcbcbc;
      border: 1px solid #bcbcbc;
      margin: 50px 0 0 300px;
      position: relative;
    }
    .absolute-box {
      position: absolute;
      height: 200px; width: 200px;
      top: 50px; left: 50px;
      color: #e55c3c;
      font-weight: bold;
      text-align: center;
      background: #2E303D;
      line-height: 200px;
    }
  </style>
</head>
<body>
  <div class='parent'>
    <div class='absolute-box'>absolute box (in parent)</div>
  </div>
  <div class='absolute-box'>absolute box (no parent)</div></body>
</html>
">
</iframe>

relative 프로퍼티와 absolute 프로퍼티의 차이점은 아래와 같다. 

relative 프로퍼티는 기본 위치(static으로 지정되었을 때의 위치)를 기준으로 좌표 프로퍼티(top, bottom, left, right)을 사용하여 위치를 이동시킨다. 따라서 무조건 부모를 기준으로 위치하게 된다. 

absolute 프로퍼티는 부모에 static 이외의 position 프로퍼티가 지정되어 있을 경우에만 부모를 기준으로 위치하게 된다. 만일 부모, 조상이 모두 static 프로퍼티인 경우, document body를 기준으로 위치하게 된다.

따라서 absolute 프로퍼티 요소는 부모 요소의 영역을 벗어나 자유롭게 어디든지 위치할 수 있다.

``` html

```
### ***result***

<iframe width='100%' height='200px' srcdoc="

">
</iframe>