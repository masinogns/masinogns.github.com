---
layout: post
title: URI and URL
categories: Interview
tag: 기술면접, 지식, 웹
---
![](http://cdqy.lite.imgeng.in/w_773/h_329/http://webtechsharing.com/wp-content/uploads/2015/11/URI.png)

### URI(Uniform Resource Identifier)

URI는 리소스를 식별하기 위해 문자열 전반을 나타낸다.<br>
<p>해당 리소스를 식별할 수 있는 식별정보</p>

### URL(Uniform Resource Locator )

URL은 리소스의 장소를 타나낸다.<br>
<p>해당 리소스의 정확한 위치</p>
<strong>'리소스의 위치'라는 것은 결국은 '하나의 파일 위치'를 나타내는 것임을 명심하자.</strong>

 <p>흔히 웹 사이트 주소로 알고 있지만, URL은 웹 사이트 주소뿐만 아니라 컴퓨터 네트워크상의 자원을 모두 나타낼 수 있다.</p>


### URI and URL 예제


##### URL

<ul>
<li>http://www.google.com/img/korea/river.jpg</li>
'river.jpg라는 인터넷 상의 해당 리소스의 정확한 위치 정보를 포함한다. 이는 URI이면서 URL이라고 말할 수 있다.'
<li>최근들어서는 홈페이지 주소역시 보안상, 디자인상, 유지보수상의 이유로 정확한 위치정보를 포함하지 않는경우가 많다.
</li>
</ul>


##### URI

<ul>
<li>http://www.google.com/img/korea/river</li>
'river라는 자원에 접근하고 싶은데 정확한 위치정보를 포함하지는 않는다.'<br>
'똑같은 river.jpg를 볼 수 있지만 river라는 식별자로 자원에 접근한다.'
<li></li>
</ul>

### 요즘에는..

<p>네이버에서 무한도전 예능 기사 URI를 가지고와 봤다.</p>

http://entertain.naver.com/read?oid=109&aid=0003573633&gid=999339&cid=1065924

<strong>read? 부분이 보인다.</strong>
<p>read? 뒤에 query 부분을 채워 넣어서 요청을 하면 해당 Query에 해당하는 문서를 볼 수 있다.</p>

<p><strong>즉, 리소스의 위치로써 리소스를 접근하는 것이 아니라 Query set을 이용해서 리소스에 접근한다는 것이다.</strong></p>

<p>URL이 아니라 URI를 뜻한다.</p>

##### 최근들어서는 홈페이지 주소역시 보안상, 디자인상, 유지보수상의 이유로 정확한 위치정보를 포함하지 않는경우가 많다.

##### 이것은 Restful한 URI 설계 때문에 그런 것 같다.

### 출처

[URI URL](http://marlboroyw.tistory.com/280)<br>
[프로그래머 인생길..](http://lambdaexp.tistory.com/39)
