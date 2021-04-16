---
title: html5 day 1
date: 2021-04-12 16:36:30
tags: html5
categories: [html]
---
# 1. HTML5
1. HTML(HyperText Markup Language)
- Markup Language 란? 
> 태그 등을 이용하여 문서나 데이터의 구조를 명기하는 언어의 한가지 
> 태그: 문서의 골격에 해당하는 부분을 작성, 원래 텍스트와는 별도로 원고의 교정부호 및 주석을 표현하기 위한 것이었으나 용도가 점차 확장되어 문서의 구조를 표현하는 역할을 하게됨
> 일반적으로는 데이터를 기술하는 정도로만 사용되기 때문에 프로그래밍 언어와는 구분됨

- HTML (HyperText Markup Language)
> 웹페이지를 기술하기 위한 마크업 언어이다. 웹페이지의 내용(content)과 구조(structure)을 담당하는 언어로써 HTML 태그를 통해 정보를 구조화하는 것이다.

- HTML5 
> 2014년 10월 28일 확정된 차세대 웹 표준으로 아래와 같은 기능들이 추가됨
> 멀티미디어(Multimedia)
	# 플래시와 같은 플러그인의 도움없이 비디오 및 오디오 기능을 자체적으로 지원한다.
> 그래픽(Graphics & Effects)
	# SVG, 캔버스를 사용한 2차원 그래픽과 CSS3, WebGL을 사용한 3차원 그래픽을 지원한다.
> 통신(Connectivity)
	# 지금까지의 HTML은 단방향 통신만이 가능하였스나 HTML5는 서버와의 소켓통신을 지원하므로 서버와의 양방향 통신이 가능하다.
> 디바이스 접근(Device acess)
	# 카메라, 동작센서 등의 하드웨어 기능을 직접적으로 제어할 수 있다.
> 오프라인 및 저장소(Offline & Storage)
	# 오프라인 상태에서도 애플리케이션을 동작시킬 수 있다. 이는 HTML5가 플랫폼으로서 사용될 수 있음을 의미한다.
> 시맨틱 태그(Semantics)
	# HTML 요소의 의미를 명확히 설명하는 시맨틱 태그를 도입하여 브라우저, 검색엔진, 개발자 모두에게 콘텐츠의 의미를 명확히 설명할 수 있다. 이를 통해 HTML 요소의 의미를 명확히 해석하고 그 데이터를 활용할 수 있는 시맨틱 웹을 실현할 수 있다.
> CSS3
	# CSS3를 지원한다.


# 2. HTML5의 기본 문법
- 요소 (Element)
> HTML요소는 시작태그와 종료태그 그리고 태그사이에 위치한 content로 구성된다.
> 태그는 대소문자를 구별하지 않으나 HTML4의 경우 소문자를 추천하고 있으므로 HTML5에서도 소문자를 사용하는것이 일반적

- 어브리뷰트 (Attribute)
> Attribute란 요소의 성질, 특징을 정의하는 명세이다. 
> 시작태그에 위치해야 하며 이름과 값의 쌍을 이룬다.

- 주석 (Comments)
> 주석은 주로 개발자에게 코드를 설명하기 위해 사용되며 브라우저는 주석을 화면에 표시하지 않는다.

# 3. 시맨틱 웹 (Semantic Web) - 의미론적 웹?
- SEO(검색엔진 최적화: Search Engin Optimization) 
> 마케팅 도구를 사용하여 검색엔진이 본인의 웹사이트를 검색하기 알맞은 구조로 웹사이트를 조정하기도 한다. 
> 이것은 기본적으로 검색엔진이 웹사이트 정보를 어떻게 수집하는지 아는것으로 부터 시작된다.

- 검색엔진
> 검색엔진은 로봇(Robot)이라는 프로그램을 이용해 매일 전세계의 웹사이트 정보를 수집한다.(이것을 크롤링이라 하며 검색엔진의 크롤러가 이를 수행)
> 그리고 검색 사이트 이용자가 검색할 만한 키워드를 미리 예상하여 검색 키워드에 대응하여 검색 키워드에 대응하는 인덱스(색인)을 만들어 둔다.(이것을 인덱싱이라 하며, 검색엔진의 인덱서가 이를 수행)
> 인덱스를 생성할 때 사용되는 정보는 검색 로봇이 수집한 정보인데 결국 웹사이트의 HTML 코드이다. 
> 즉, 검색엔진은 HTML 코드만으로 그 의미를 인지하여야 하는데 이때 시맨틱 요소 (Semantic element)를 해석하게 된다.

- 시맨틱 태그란
> 브라우저, 검색엔진, 개발자 모두에게 콘텐츠의 의미를 명확히 설명하는 역할을 한다.

- 시맨틱 웹이란
> 웹에 존재하는 수많은 웹페이지들에 메타데이터(Metadata)를 부여하여, 기존의 잡다한 데이터 집합이었던 웹페이지를 의미와 관련성을 가지는 거대한 데이터베이스로 구축하고자 하는 발상

- HTML 요소는 non-semetic 요소, semantic 요소로 구분할 수 있다.
> non-semantic 요소: div, span 등이 있으며 이들 태그는 content에 대하여 어떤 설명도 하지 않는다. 
> semantic 요소: form, table, img 등이 있으며 이들 태그는 content의 의미를 명확히 설명한다.


# 4. HTML5 Tag - Basic
- 문서 형식 정의 tag
> HTML5
```html
<!DOCTYPE html>
```

- html tag
> html 태그는 모든 HTML 요소의 부모 요소이며 웹페이지에 단 하나만 존재한다. 즉, 모든 요소는 html 요소의 자식 요소이며 html 요소 내부에 기술해야한다.
단, 
```html
<!DOCTYPE html>
``` 
는 예외

- head tag
> head 요소는 메타데이터를 포함하기 위한 요소
1.1 title tag
> title 요소는 문서의 제목을 정의한다. 정의된 제목은 브라우저의 탭에 표시된다. 

1.2 style tag
> style 요소에는 HTML 문서를 위한 sytle 정보를 정의한다. 

1.3 link tag
> link 요소에는 외부 리소스와의 연계 정보를 정의한다. 주로 HTML과 외부 CSS 파일을 연계에 사용된다.

1.4 script tag
> script 요소에는 client-side javascript를 정의한다.
```html
<script src="main.js"></script>
```
1.5 meta tag
> meta 요소는 description, keytwords, author, 기타 메타데이터 정의에 사용된다. 메타데이터는 브라우저, 검색엔진(keywords)등에 의해 사용된다.
> charset 어브리뷰트는 브라우저가 사용할 문자셋을 정의한다.
```html
<meta charset="utf-8">
```
> SEO(검색엔진 최적화)를 위해 검색엔진이 사용할 keywords를 정의한다.
```html 
<meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript">
```
> 웹페이지의 설명을 정의한다. 
```html
<meta name="description" content="Web tutorials on HTML and CSS">
```
> 웹페이지의 저자를 명기한다. 
```html
<meta name="author" content="John Doe">
```
> 웹페이지를 30초 마다 Refresh 한다.
```html
<meta http-equiv="refresh" content="30">
```

- body tag
> body tag는 HTML 문서의 내용을 나타내며 웹페이지에 단 하나만 존재한다. 
> 메타데이터를 제외한 웹페이지를 구성하는 대부분의 요소가 body 요소내에 기술된다.

```html
  <body>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
  </body>
```



* 메타데이터: 메타데이터(metadata)는 데이터(data)에 대한 데이터이다. 이렇게 흔히들 간단히 정의하지만 엄격하게는, Karen Coyle에 의하면 "어떤 목적을 가지고 만들어진 데이터 (Constructed data with a purpose)"라고도 정의한다.
* SPA: single page application



















