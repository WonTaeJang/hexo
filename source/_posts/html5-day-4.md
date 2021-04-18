---
title: html5-day-4
date: 2021-04-17 15:03:00
tags: 
    - html 
    - tag 
    - img
    - video
    - audio
categories: 
    - html
---

### HTML5 Tag - Image & Multimedia
## 이미지의 표현과 동영상, 음악 등 멀티미디어를 지원하는 태그 

# 1. 이미지 
웹페이지에 이미지를 삽입하는 경우, img tag를 사용한다.

|attribute|Description|
|-----------|---------------------------|
|src|이미지 파일 경로|
|alt|이미지 파일이 없을 경우 표시되는 문장|
|width|이미지의 너비 (CSS에서 지정하는 것이 일반적|
|height|이미지의 높이 (CSS에서 지정하는 것이 일반적)|

``` html
<!DOCTYPE html>
<html>
  <body>
    <img src="img/cat.png" alt="cat" width="100">
    <img src="img/catcat.gif" alt="이미지가 없습니다.">
  </body>
</html>
```

<!DOCTYPE html>
<html>
  <body>
    <img src="img/cat.png" alt="cat" width="100">
    <img src="img/catcat.gif" alt="이미지가 없습니다.">
  </body>
</html>

# 2. 미디어
## 2.1 audio
audio 태그는 HTML5에서 새롭게 추가된 태그이다. IE8 이하에서는 사용할 수 없다.

|attribute|Description|
|-----------|---------------------------|
|src|음악 파일 경로|
|preload|재생 전에 음악 파일을 모두 불러올 것인지 지정|
|autoplay|음악 파일을 자동 재생 개시할 것인지 지정|
|loop|음악을 반복할 것인지 지정|
|controls|음악 재생 도구를 표시할 것인지 지정. 재생 도구의 외관은 브라우저마다 차이가 있다.|

``` html
<!DOCTYPE html>
<html>
  <body>
    <audio src="/audio/test.mp3" controls></audio>
  </body>
</html>
```

## 2.2 비디오
video 태그는 HTML5에서 새롭게 추가된 태그이다. IE8 이하에서는 사용할 수 없다. 

|attribute|Description|
|-----------|---------------------------|
|src|동영상 파일 경로|
|poster|동영상 준비 중에 표시될 이미지 파일 경로|
|preload|재생 전에 동영상 파일을 모두 불러올 것인지 지정|
|autoplay|동영상 파일을 자동 재생 개시할 것인지 지정(Chrome의 경우 mute를 설정해야지만 재생가능)|
|loop|동영상을 반복할 것인지 지정|
|controls|동영상 재생도구를 표시할 것인지 지정, 재생도구의 외관은 브라우저마다 차이가 있다.|
|width|동영상의 너비를 지정|
|height|동영상의 높이를 지정|

``` html
<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
Your browser does not support the video tag.
</video>
```