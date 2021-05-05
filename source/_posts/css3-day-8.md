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