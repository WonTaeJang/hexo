---
title: css3-day-15
date: 2021-05-26 17:29:56
    - css 
    - animation
categories: 
    - css
---

### CSS3 Animation
## 애니메이션

애니메이션(Animation)효과는 HTML 요소에 적용되는 CSS 스타일을 다른 CSS 스타일로 부드럽게 변화시킨다. 애니메이션은 애니메이션을 나타내는 CSS 스타일과 애니메이션 sequence를 나타내는 복수의 키프레임(@keyframes)들로 이루어진다. 

transition으로도 어느정도의 애니메이션 효과를 표현할 수 있으나 animation보다는 제한적이다. 일반적으로 트랜지션 효과는 요소 프로퍼티값이 다른 값으로 변화할 때 주로 사용하며 요소의 로드와 함께 자동으로 발동되지 않는다. :hover와 같은 가상 클래스 선택자(Pseudo-Class Selector)또는 자바스크립트의 이벤트와 같은 부수적 액션에 의해 발동된다.

즉 transition 프로퍼티는 단순히 요소의 프로퍼티 변화에 주안점이 있다면 animation 프로퍼티는 하나의 줄거리를 구성하여 줄거리 내에서 세부 움직임을 시간흐름 단위로 제어할 수 있고 전체 줄거리의 재생과 정지, 반복까지 제어할 수 있다. 

일반적으로 CSS 애니메이션을 사용하면 기존의 JavaScript 기반 애니메이션 실행과 비교하여 더 나은 렌더링 성능을 제공한다고 알려져 있다. 그러나 경우에 따라서는 JavaScript를 사용하는 것이 나을 수도 있다. jQuery 등의 애니메이션 기능은 CSS보다 간편하게 애니메이션 효과를 가능케 한다. 

- 비교적 작은 효과나 CSS만으로도 충분한 효과를 볼 수 있는 것은 CSS를 사용한다. 예를 들어 요소의 width 변경 애니메이션은 자바스크립트를 사용하는 것보다 훨씬 간편하며 효과적이다. 
- 세밀한 제어를 위해서는 자바스크립트 사용이 바람직하다. 예를 들어 바운스, 중지, 일시중지, 되감기 또는 감속과 같은 고급 효과는 자바스크립트가 훨씬 유용하다. 

가장 중요한 것은 브라우저에서 애니메이션 효과가 부드럽게 실행되는 것이다. 그리고 애니메이션 효과 작성에 소요되는 시간과 수고이다. 여러 사항들을 고려하여 자바스크립트를 사용하여야 할지 CSS를 사용하여야 할지 결정하여야 한다. 

|프로퍼티|설명|기본값|
|--------|----|------|
|animation-name|@keyframe 애니메이션 이름을 지정한다||
|animation-duration|한 싸이클의 애니메이션에 소요되는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다|0s|
|animation-timing-function|애니메이션 효과를 위한 타이밍 함수를 지정한다|ease|
|animation-delay|요소가 로드된 시점과 애니메이션이 실제로 시작하는 사이에 대기하는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다|0s|
|animation-iteration-count|애니메이션 재생 횟수를 지정한다|1|
|animation-direction|애니메이션이 종료된 이후 반복될 때 진행하는 방향을 지정한다|normal|
|animation-fill-mode|애니메이션 미실행 시(종료 또는 대기) 요소의 스타일을 지정한다.||
|animation-play-state|애니메이션 재생 상태(재생 또는 중지)를 지정한다|running|
|animation|모든 애니메이션 프로퍼티를 한번에 지정한다(shorthand syntax)||

# 1. @keyframes
- [@keyframes](https://developer.mozilla.org/ko/docs/Web/CSS/@keyframes)

CSS 애니메이션과 트랜지션 방식의 주된 차이는 @keyframes rule에 있다. 이 rule을 사용하면 애니메이션의 흐름(sequence)중의 여러 시점(breakpoint)에서 CSS 프로퍼티값을 지정할 수 있다.

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    div {
      position: absolute;
      width: 100px;
      height: 100px;
      background-color: red;
      animation-name: move;
      animation-duration: 5s;
      animation-iteration-count: infinite;
    }
    /* @keyframes rule */
    @keyframes move {
      /* keyframe */
      from {
        left: 0;
      }
      /* keyframe */
      to {
        left: 300px;
      }
    }
  </style>
</head>
<body>
  <div></div>
</body>
</html>
```
### ***result***

<iframe width='100%' height='130px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    div {
      position: absolute;
      width: 100px;
      height: 100px;
      background-color: red;
      animation-name: move;
      animation-duration: 5s;
      animation-iteration-count: infinite;
    }
    /* @keyframes rule */
    @keyframes move {
      /* keyframe */
      from {
        left: 0;
      }
      /* keyframe */
      to {
        left: 300px;
      }
    }
  </style>
</head>
<body>
  <div></div>
</body>
</html>
">
</iframe>

@keyframes rule은 시간의 흐름에 따라 애니메이션을 정의한다. 여러 개의 키프레임을 정의하거나 애니메이션 중에 특정 CSS프로퍼티에 값을 지정하는 지점을 정의할 수 있다.

위 예제를 보면 @keyframes 뒤에 애니메이션을 대표하는 임의의 이름을 부여하였다. 

``` css
@keyframes move {}
```

from, to 키워드를 사용하여 애니메이션의 시작과 끝 시점을 정의하였다. 그리고 애니메이션의 시작 시점을 의미하는 from 키프레임 내에서 left 프로퍼티에 값 0을, 애니메이션의 끝 시점을 의미하는 to 키프레임 내에서 left 프로퍼티에 값 300px을 지정하였다. 그 결과, 정지 상태에서 오른쪽으로 300px 이동하는 애니메이션이 실행된다.

``` css 
@keyframes move {
  /* 애니메이션 시작 시점 */
  from { left: 0; }
  /* 애니메이션 종료 시점 */
  to   { left: 300px; }
}
```

from, to 키워드 대신 %를 사용할 수 있다. 또한 시작과 끝 키프레임 사이에 % 단위로 키프레임을 삽입할 수 있다. 

``` css
@keyframes move {
  0%   { left: 0; }
  50%  { left: 100px; }
  100% { left: 300px; }
}
```

# 2.animation-name
위 예제를 보면 @keyframes 뒤에 애니메이션을 대표하는 임의의 이름을 부여하였다. 

``` css
  @keyframes move{}
```
이 이름을 animation-name 프로퍼티값으로 지정하여 사용하고자 하는 @keyframes rule을 선택한다. 하나 이상의 애니메이션 이름을 지정할 수 있다. 

``` html
<!DOCTYPE html>
<html>
<head>
  <style>
    div {
      position: absolute;
      width: 100px;
      height: 100px;
      animation-name: move, fadeOut, changeColor;
      animation-duration: 5s;
      animation-iteration-count: infinite;
    }
    @keyframes move {
      from { left: 0; }
      to   { left: 300px; }
    }
    @keyframes fadeOut {
      from { opacity: 1; }
      to   { opacity: 0; }
    }
    @keyframes changeColor {
      from { background-color: red; }
      to   { background-color: blue; }
    }
  </style>
</head>
<body>
  <div></div>
</body>
</html>
```
### ***result***

<iframe width='100%' height='130px' srcdoc="
<!DOCTYPE html>
<html>
<head>
  <style>
    div {
      position: absolute;
      width: 100px;
      height: 100px;
      animation-name: move, fadeOut, changeColor;
      animation-duration: 5s;
      animation-iteration-count: infinite;
    }
    @keyframes move {
      from { left: 0; }
      to   { left: 300px; }
    }
    @keyframes fadeOut {
      from { opacity: 1; }
      to   { opacity: 0; }
    }
    @keyframes changeColor {
      from { background-color: red; }
      to   { background-color: blue; }
    }
  </style>
</head>
<body>
  <div></div>
</body>
</html>
">
</iframe>

# 3. animation-duration
한 싸이클의 애니메이션에 소요되는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다. 

``` code
  animation-duration: .5s;
  animation-duration: 500ms;
```

animation-duration은 반드시 지정해야 한다. 지정하지 않는 경우 기본값 0s가 셋팅되어 어떠한 애니메이션도 실행되지 않는다. 

# 4. animation-timing-function
애니메이션 효과를 위한 수치 함수를 지정한다. 수치 함수에 대한 설명은 트랜지션 transtition-timing-function 프로퍼티를 참조.

# 5. animation-delay
요소가 로드된 시점과 애니메이션이 실제로 시작하는 사이에 대기하는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다. 

``` code
  animation-delay: 2s;
```

# 6. animation-iteration-count
애니메이션 주기의 재생 횟수를 지정한다. 기본값은 1이며 infinite로 무한반복 할 수 있다. 

``` code
  animation-iteration-count: 3;
```


``` html

```
### ***result***

<iframe width='100%' height='130px' srcdoc="

">
</iframe>