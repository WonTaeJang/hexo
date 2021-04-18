---
title: html5-day-5
date: 2021-04-18 16:00:28
tags:
    - html 
    - tag 
    - form
categories: 
    - html
---

### HTML5 Tag - Forms
## 사용자와의 커뮤니케이션을 위한 폼 태그

# 1.form
form 태그는 사용자가 입력한 데이터를 수집하기 위해 사용되며 input, textarea, button, select, checkbox, rado button, submit button 등의 입력 양식 태그를 포함할 수 있다. 

``` html
<form>
...
form elements (input, checkbox, radio button, submit button...)
...
</form>
```

|attribute|value|Description|
|---------|-----|-----------|
|action|URL|입력데이터(form data)가 전송될 URL 지정|
|method|get/post|입력 데이터(form data)전달 방식 지정|

GET과 POST는 HTTP프로토콜을 이용해서 사용자 입력 데이터를 서버에 전달하는 방식을 나타내며 HTTP request method라 한다.
> Get
> - GET 방식은 전송 URL에 입력데이터를 쿼리스트링으로 보내는 방식이다.      
> 예) http://testURL.com/id=4444&pw=1234
> - 전송 URL 바로 뒤에 '?'를 통해 데이터의 시작을 알려주고, key-value형태의 데이터를 추가한다. 1개 이상의 전송데이터는 '&'로 구분한다.
> - URL에 전송 데이터가 모두 노출되기 때문에 보안에 문제가 있으며 전송할 수 있는 데이터의 한계가 있다. (최대 255자).
> - REST API에서 GET 메소드는 모든 또는 특정 리소스의 조회를 요청한다.

> POST
> - POST 방식은 Request Body에 담아 보내는 방식이다.
> URL에 전송 데이터가 모두 노출되지 않지만 GET에 비해 속도가 느리다. 
> REST API에서 POST 메소드는 특정 리소스의 생성을 요청한다.

``` html 
<!DOCTYPE html>
<html>
  <body>
    <form action="https://wontaejang.github.io/" method="get">
      ID: <input type="text" name="id" value="1"><br>
      username: <input type="text" name="username" value="WT.Jang"><br>
      <input type="submit" value="Submit">
    </form>
  </body>
</html>
```

<!DOCTYPE html>
<html>
  <body>
    <form action="https://wontaejang.github.io/" method="get">
      ID: <input type="text" name="id" value="1"><br>
      username: <input type="text" name="username" value="WT.Jang"><br>
      <input type="submit" value="Submit">
    </form>
  </body>
</html>

submit button이 클릭되면 input 태그에 입력된 데이터가 form 태그의 method어트리뷰트에 지정된 방식으로 action 어트리뷰트에 지정된 서버측의 처리 로직에 전달 된다.

# 2.input
input 태그는 form 태그 중에서 가장 중요한 태그로 사용자로부터 데이터를 입력받기위해 사용된다.   
input 태그는 다양한 종류가 있는데 type 어트리뷰트에 의해 구분된다. form 태그 내에 존재하여야 입력 데이터를 전송할 수 있으나 ajax를 사용할 시에는 form 태그 내에 존재하지 않아도 된다. 

서버에 전송되는 데이터는 name 어트리뷰터를 키로, value 어트리뷰트를 값으로하여 key = value의 형태로 전송된다. 

``` html
<!DOCTYPE html>
<html>
  <body>
    <h3>button</h3>
    <input type="button" value="Click me" onclick="alert('Hello world!')">
    <hr>

    <h3>checkbox</h3>
    <input type="checkbox" name="fruit1" value="apple" checked> 사과<br>
    <input type="checkbox" name="fruit2" value="grape"> 포도<br>
    <input type="checkbox" name="fruit3" value="peach"> 복숭아<br>
    <hr>

    <h3>color</h3>
    <input type="color" name="mycolor">
    <hr>

    <h3>date</h3>
    <input type="date" name="birthday">
    <hr>

    <h3>datetime</h3>
    <input type="datetime" name="birthdaytime">
    <hr>

    <h3>datetime-local</h3>
    <input type="datetime-local" name="birthdaytime">
    <hr>

    <h3>email</h3>
    <input type="email" name="useremail">
    <hr>

    <h3>file</h3>
    <input type="file" name="myfile">
    <hr>

    <h3>hidden</h3>
    <input type="hidden" name="country" value="Norway">
    hidden filed는 사용자에 표시되지 않는다.
    <hr>

    <h3>image</h3>
    <input type="image" src="img/img_submit.gif" alt="Submit" width="48" height="48">
    <hr>

    <h3>month</h3>
    <input type="month" name="birthdaymonth">
    <hr>

    <h3>number</h3>
    <input type="number" name="quantity" min="2" max="10" step="2" value="2">
    <hr>

    <h3>password</h3>
    <input type="password" name="pwd">
    <hr>

    <h3>radio</h3>
    <input type="radio" name="gender" value="male" checked> 남자<br>
    <input type="radio" name="gender" value="female"> 여자<br>
    <hr>

    <h3>range</h3>
    <input type="range" name="points" min="0" max="10" step="1" value="5">
    <hr>

    <h3>reset</h3>
    <input type="reset">
    <hr>

    <h3>search</h3>
    <input type="search" name="googlesearch">
    <hr>

    <h3>submit</h3>
    <input type="submit" value="Submit">
    <hr>

    <h3>tel</h3>
    <input type="tel" name="mytel">
    <hr>

    <h3>text</h3>
    <input type="text" name="myname">
    <hr>

    <h3>time</h3>
    <input type="time" name="mytime">
    <hr>

    <h3>url</h3>
    <input type="url" name="myurl">
    <hr>

    <h3>week</h3>
    <input type="week" name="week_year">
  </body>
</html>
```

<!DOCTYPE html>
<html>
  <body>
    <h3>button</h3>
    <input type="button" value="Click me" onclick="alert('Hello world!')">
    <hr>
    <h3>checkbox</h3>
    <input type="checkbox" name="fruit1" value="apple" checked> 사과<br>
    <input type="checkbox" name="fruit2" value="grape"> 포도<br>
    <input type="checkbox" name="fruit3" value="peach"> 복숭아<br>
    <hr>
    <h3>color</h3>
    <input type="color" name="mycolor">
    <hr>
    <h3>date</h3>
    <input type="date" name="birthday">
    <hr>
    <h3>datetime</h3>
    <input type="datetime" name="birthdaytime">
    <hr>
    <h3>datetime-local</h3>
    <input type="datetime-local" name="birthdaytime">
    <hr>
    <h3>email</h3>
    <input type="email" name="useremail">
    <hr>
    <h3>file</h3>
    <input type="file" name="myfile">
    <hr>
    <h3>hidden</h3>
    <input type="hidden" name="country" value="Norway">
    hidden filed는 사용자에 표시되지 않는다.
    <hr>
    <h3>image</h3>
    <input type="image" src="img/cat.png" alt="Submit" width="48" height="48">
    <hr>
    <h3>month</h3>
    <input type="month" name="birthdaymonth">
    <hr>
    <h3>number</h3>
    <input type="number" name="quantity" min="2" max="10" step="2" value="2">
    <hr>
    <h3>password</h3>
    <input type="password" name="pwd">
    <hr>
    <h3>radio</h3>
    <input type="radio" name="gender" value="male" checked> 남자<br>
    <input type="radio" name="gender" value="female"> 여자<br>
    <hr>
    <h3>range</h3>
    <input type="range" name="points" min="0" max="10" step="1" value="5">
    <hr>
    <h3>reset</h3>
    <input type="reset">
    <hr>
    <h3>search</h3>
    <input type="search" name="googlesearch">
    <hr>
    <h3>submit</h3>
    <input type="submit" value="Submit">
    <hr>
    <h3>tel</h3>
    <input type="tel" name="mytel">
    <hr>
    <h3>text</h3>
    <input type="text" name="myname">
    <hr>
    <h3>time</h3>
    <input type="time" name="mytime">
    <hr>
    <h3>url</h3>
    <input type="url" name="myurl">
    <hr>
    <h3>week</h3>
    <input type="week" name="week_year">
  </body>
</html>                

# 3. select
복수개의 리스트에서 복수개의 아이템을 선택할 때 사용한다. 함께 사용할 수 있는 태그는 다음과 같다.       

서버에 전송되는 데이터는 select 요소의 name 어트리뷰트를 키로, option 요소의 value 어트리뷰트를 값으로 하여 key=value의 형태로 전송된다. 

|tag|Description|
|---|-----------|
|select|select form 생성|
|option|option 생성|
|optgroup|option을 그룹화한다.|
 
```html
<!DOCTYPE html>
<html>
  <body>
    <select name="cars1">
      <option value="volvo" selected>Volvo</option>
      <option value="saab" disabled>Saab</option>
      <option value="fiat">Fiat</option>
      <option value="audi">Audi</option>
    </select>

    <select name="cars2" size="4" multiple>
      <option value="volvo">Volvo</option>
      <option value="saab">Saab</option>
      <option value="fiat">Fiat</option>
      <option value="audi" selected>Audi</option>
    </select>

    <select name="cars3">
      <optgroup label="Swedish Cars">
        <option value="volvo">Volvo</option>
        <option value="saab">Saab</option>
      </optgroup>
      <optgroup label="German Cars" disabled>
        <option value="mercedes">Mercedes</option>
        <option value="audi">Audi</option>
      </optgroup>
    </select>
  </body>
</html>
```

<!DOCTYPE html>
<html>
  <body>
    <select name="cars1">
      <option value="volvo" selected>Volvo</option>
      <option value="saab" disabled>Saab</option>
      <option value="fiat">Fiat</option>
      <option value="audi">Audi</option>
    </select>
    <select name="cars2" size="4" multiple>
      <option value="volvo">Volvo</option>
      <option value="saab">Saab</option>
      <option value="fiat">Fiat</option>
      <option value="audi" selected>Audi</option>
    </select>
    <select name="cars3">
      <optgroup label="Swedish Cars">
        <option value="volvo">Volvo</option>
        <option value="saab">Saab</option>
      </optgroup>
      <optgroup label="German Cars" disabled>
        <option value="mercedes">Mercedes</option>
        <option value="audi">Audi</option>
      </optgroup>
    </select>
  </body>
</html>

# 4. textarea
textarea 태그는 여러 줄의 글자를 입력할 때 사용한다.

```html
<!DOCTYPE html>
<html>
  <body>
    <textarea name="message" rows="10" cols="30">Write something here</textarea>
  </body>
</html>
```

<!DOCTYPE html>
<html>
  <body>
    <textarea name="message" rows="10" cols="30">Write something here</textarea>
  </body>
</html>

# 5. button 
button 태그는 클릭할 수 있는 버튼을 생성한다. **```<input type="button">```** 과 유사하지만 input 태그는 빈 태그인 반면 button 태그는 그렇지 않다. 따라서 button 요소에는 텍스트나 이미지 같은 콘텐츠를 사용할 수 있다. 

type 어트리뷰트는 반드시 지정하는 것이 바람직하며 어트리뷰트 값으로 button, reset, submit를 지정할 수 있다. 

```html
<!DOCTYPE html>
<html>
  <body>
    <button type="button" onclick="alert('Hello World!')">Click Me!</button>

    <input type="button" value="Click Me!" onclick="alert('Hello world!')">
  </body>
</html>
```
<!DOCTYPE html>
<html>
  <body>
    <button type="button" onclick="alert('Hello World!')">Click Me!</button>
    <input type="button" value="Click Me!" onclick="alert('Hello world!')">
  </body>
</html>

button 태그는 어트리뷰트만을 받아들이는 input 태그와 달리 콘텐츠로 문자열은 물론 HTML 요소를 받을 수도 있다는 장점이 있다. submit의 경우 브라우저마다 다를 수 있다. 

```html 
<button type="submit" name="myButton" value="foo">Click me</button>
```

# 6.fieldset / legend
fieldset 태그는 관련된 입력 양식들을 그룹화 할 때 사용한다. legend 태그는 fieldset 태그 내에서 사용되야 하며 그룹화된 fieldset의 제목을 정의한다.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
  </head>
  <body>
      <fieldset>
        <legend>Login</legend>
        Username <input type="text" name="username">
        Password <input type="text" name="password">
      </fieldset>
  </body>
</html>
```

<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
  </head>
  <body>
      <fieldset>
        <legend>Login</legend>
        Username <input type="text" name="username">
        Password <input type="text" name="password">
      </fieldset>
  </body>
</html>