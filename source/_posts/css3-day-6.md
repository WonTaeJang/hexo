---
title: css3-day-6
date: 2021-05-02 23:11:38
    - css 
    - background
categories: 
    - css
---

# css3 Background
Background 관련 프로퍼티는 해당 요소의 배경으로 이미지 또는 색상을 정의한다. 

자세한 내용은 [CSS Background and Borders](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Backgrounds_and_Borders)를 참조한다.

# 1. background-image 프로퍼티
요소에 배경 이미지를 지정한다. 
- [MDN:background-image](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image)

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      background-image: url('../img/cat.png');
    }
  </style>
</head>
<body>
  <h3>Background Image</h3>
</body>
</html>
```
### ***result***

<iframe width='100%' height='350px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      background-image: url('../img/cat.png');
    }
  </style>
</head>
<body>
  <h3>Background Image</h3>
</body>
</html>
">
</iframe>

# 2.background-repeat 프로퍼티
배경 이미지의 반복을 지정한다. 수직, 수평 또는 수직과 수평 모두의 반복을 지정할 수 있다. 

설정된 이미지의 크기가 화면보다 작으면 자동으로 이미지가 반복 출력되어 화면을 채우게 된다. 이것을 background-repeat 프로퍼티의 기본값이 repeat 이기 때문이다. 

x축으로만 배경 이미지를 반복할 경우, background-repeat 프로퍼티값에 repeat-x, y축으로만 배경 이미지를 반복할 경우, repeat-y 를 설정한다.

- [MDN:background-repeat](https://developer.mozilla.org/en-US/docs/Web/CSS/background-repeat)

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      background-image: url('../img/cat.png');
      background-repeat: repeat-x;
    }
  </style>
</head>
<body>
  <h3>background-repeat: repeat-x;</h3>
</body>
</html>
```
### ***result***

<iframe width='100%' height='250px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      background-image: url('../img/cat.png');
      background-repeat: repeat-x;
    }
  </style>
</head>
<body>
  <h3>background-repeat: repeat-x;</h3>
</body>
</html>
">
</iframe>

반복 출력을 멈추고 싶은 경우, background-repeat 프로퍼티값에 no-repeat를 설정한다.

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      background-image: url('../img/cat.png');
      background-repeat: no-repeat;
    }
  </style>
</head>
<body>
  <h3>background-repeat: no-repeat;</h3>
</body>
</html>
```
### ***result***

<iframe width='100%' height='250px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      background-image: url('../img/cat.png');
      background-repeat: no-repeat;
    }
  </style>
</head>
<body>
  <h3>background-repeat: no-repeat;</h3>
</body>
</html>
">
</iframe>

background-image에 복수개의 이미지를 설정할 경우, 먼저 설정된 이미지가 전면에 출력된다.

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      background-image: url('../img/cat.png'), url('../img/og_image.png');
      background-repeat: no-repeat, repeat;
    }
  </style>
</head>
<body>
  <h3>background-repeat: no-repeat, repeat;</h3>
</body>
</html>
```
### ***result***

<iframe width='100%' height='350px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      background-image: url('../img/cat.png'), url('../img/og_image.png');
      background-repeat: no-repeat, repeat;
    }
  </style>
</head>
<body>
  <h3>background-repeat: no-repeat, repeat;</h3>
</body>
</html>
">
</iframe>

# 3. background-size 프로퍼티
배경 이미지의 사이즈를 지정한다. 배경 이미지의 고유 비율을 유지하기 때문에 설정에 따라 이미지의 일부가 보이지 않을 수 있다. 

프로퍼티값은 px, %, cover, contain 등을 사용한다. 

배경이미지의 width, height를 모두 설정할 수 있다. 이때 첫번째 값은 width, 두번째 값은 height를 의미한다. 하나의 값만을 지정한 경우, 지정한 값은 width를 의미하게 되며 height는 auto로 지정된다.

- [MDN: background-size](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size)

**px값 지정**

배경이미지 크기가 지정된 px값 그대로 설정된다. 첫번째 값은 width, 두번째 값은 height를 의미한다. 

``` css
.bg {
  background-size: 700px 500px;
}
```

**%값 지정**

배경이미지 크기가 지정된 %값에 비례하여 설정된다. 첫번째 값은 width, 두번째 값은 height를 의미한다.

화면을 줄이거나 늘리면 배경이미지의 크기가 따라서 변경되어 찌그러지는 현상이 나타난다. 

``` css
.bg {
  background-size: 100% 100%;
}
```

**cover 지정**

배경이미지의 크기 비율을 유지한 상태에서 부모 요소의 width, height 중 큰값에 배경이미지를 맞춘다. 따라서 이미지의 일부가 보이지 않을 수 있다. 

``` css
.bg {
  background-size: cover;
}
```

**contain 지정**

배경이미지의 크기 비율을 유지한 상태에서 부모 요소의 영역에 배경이미지가 보이지 않는 부분없이 전체가 들어갈 수 있도록 이미지 스케일을 조정한다.

``` css
.bg {
  background-size: contain;
}
```

width, height의 프로퍼티값은 공백으로 구분하여야 한다. 프로퍼티값을 쉼표로 구분하면 다른 배경이미지의 너비를 지정하는 것으로 인식되기 때문에 주의가 필요하다.

```css
body {
  background-image: url("front.png"), url("back.png");
  background-repeat: no-repeat, no-repeat;
  background-size: 100%, 500px;
}
```

``` html

```
### ***result***

<iframe width='100%' height='350px' srcdoc="

">
</iframe>