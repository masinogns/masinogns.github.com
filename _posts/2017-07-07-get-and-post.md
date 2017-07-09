---
layout: post
title: Get 방식과 Post 방식의 차이
categories: Interview
tag: 기술면접, 지식, 웹, http
---
### 개요

<ul>
<li>공통점</li>
<li>GET 방식</li>
<li>POST 방식</li>
<li>차이점</li>
<li>궁금한 점</li>
</ul>

### 공통점

<p></p>
<p>공통점 : 웹 페이지에서 웹 서버로 정보를 전송하는 방식이다.</p>
<p>전송 방식이 다르고 사용 목적이 다르다.</p>

### GET 방식

<ul>
<li>URL에 변수를 포함시켜서 요청한다.</li>
'URL에 데이터가 노출된다.'--> '보안에 취약할 수 있다.'
<li>데이터가 헤더에 포함되어 전달된다.</li>
<li>서버(==DB) 측에서의 정보 조회를 원할 때 사용한다.</li>
<li>길이의 제한이 있다.</li>
<li>캐시될 수 있다.</li>
<li>Read</li>
<li>검색 엔진에 검색어를 치면 URL을 이용해서 검색어에 관한 정보를 조회한다.</li>
</ul>

<p>Create, Update, Delete를 Get 방식으로 처리를 하게 된다면 URL에 요청 정보를 넣고 생성, 수정, 삭제를 수행할 수 있기 때문에 Get 방식이 아닌 Post나 Put, Delete를 사용해서 수행해야한다.</p>
<p>검색 엔즌은 Get 방식을 이용한다. 왜냐하면 외부에서 링크를 걸기 쉽게 하기 위해서 그렇다.</p>
<p>Get 방식이 Post 방식보다 빠르다. 왜냐하면 Get 방식은 캐싱을 할 수 있기 때문이다.</p>
<p>캐싱은 웹에 한 번 접근 한 후에 또 요청할 시 빠르게 접근하기 위해 데이터를 저장하기 때문이다.</p>

```
이름과 나이가 URL에 있다.
/hello/test.php?name="백기훈"&age=19
```

따라서, GET 방식에서 BODY에 특별한 내용을 넣을 것이 없으므로 BODY가 빈상태로 보내진다.

그러므로, 헤더의 내용중 BODY 데이터를 설명하는 Content-Type이라는 헤더필드는 들어가지 않는다.


### POST 방식

<ul>
<li>URL에 변수를 포함하지 않는다.</li>
'URL에 데이터가 노출되지 않는다.'-->'get보다는 보안에 유리하다.'
<li>데이터가 Body에 포함되어 전달된다.</li>
<li>서버(==DB) 측에서의 정보 갱신 작업을 원할 때 사용한다.</li>
<li>Create, Update, Delete</li>
<li>길이의 제한이 없다.</li>
<li>캐시될 수 없다.</li>
<li>회원 가입 등 어떤 일련 Form에 개인 정보를 제출할 때 사용한다.</li>
</ul>

```
이름과 나이가 HTTP Body 안에 있다.
POST /hello/test.php HTTP/1.1
Host: jmnote.com
name="백기훈"&age=19
```

POST방식은 BODY에다가 데이터를 넣어서 보낸다.  

따라서, 헤더필드중 BODY의 데이터를 설명하는 Content-Type이라는 헤더 필드가 들어가고 어떤 데이터 타입인지 명시한다.


### 근본적인 차이 : idempotent vs non-idempotent

<p>Get : idempotent : 변화가 없다.</p>
<p>해당 요청을 몇 번을 수행해도 동일한 결과가 나온다.</p>
<p>Post : non-idempotent : 변화가 있다.</p>
<p>해당 요청이 수행되면 서버에서 무엇인가 바귀고 동일한 결과가 나오는 것을 보장할 수 없다.</p>

### 궁금한 점

<p>URI를 GET 방식과 POST 방식으로만 구성하는 이유는 무엇일까?</p>
<p>Get은 캐싱을 할 수 있지만 Post는 캐싱을 할 수 없는 이유는 무엇일까?</p>
<p></p>
<p></p>
