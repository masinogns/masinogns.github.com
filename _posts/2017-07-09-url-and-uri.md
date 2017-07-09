---
layout: post
title: URI and URL
categories: Interview
tag: 기술면접, 지식, 웹
---
![](http://cdqy.lite.imgeng.in/w_773/h_329/http://webtechsharing.com/wp-content/uploads/2015/11/URI.png)

### URI(Uniform Resource Identifier)
인터넷에 있는 자원을 나타내는 유일한 주소이다.

### URL(Uniform Resource Locator )
흔히 웹 사이트 주소로 알고 있지만, URL은 웹 사이트 주소뿐만 아니라 컴퓨터 네트워크상의 자원을 모두 나타낼 수 있다. 그 주소에 접속하려면 해당 URL에 맞는 프로토콜을 알아야 하고, 그와 동일한 프로토콜로 접속해야 한다.

<strong>인터넷 상의 자원의 위치와 식별자.
언듯 보면 같은 것을 의미하는 듯 하다.
하지만 '자원의 위치'라는 것은 결국은 '하나의 파일 위치'를 나타내는 것임을 명심하자.</strong>

http://img0.gmodules.com/ig/images/korea/logo.gif
이와 같은 형식은 logo.gif라는 인터넷상의 자원 위치를 의미 한다.
이는 URI이면서도 URL라고 말할 수 있다.
해당 리소스의 정확한 위치정보를 포함하고 있기 때문이다.

최근들어서는 홈페이지 주소역시 보안상, 디자인상, 유지보수상의 이유로 정확한 위치정보를 포함하지 않는경우가 많다.

다음은 어떠한가.
http://endic.naver.com/endic.nhn?docid=1232950
http://endic.naver.com/란 서버에 위치한 endic.nhn파일은 query string인 docid의 값에 따라 여러가지 결과를 나타낸다.

여기서 URL은 endic.nhn의 위치를 표기한 http://endic.naver.com/endic.nhn 까지이다.
내가 원하는 정보에 도달 하기위해서는 ?docid=1232950라는 식별자(Identifier)가 필요한 것이다.

결국 위의 http://endic.naver.com/endic.nhn?docid=1232950 주소는 URI이긴 하지만 URL은 아니다.


출처: http://lambdaexp.tistory.com/39 [프로그래머 인생길..]</strong>


http://www.naver.com/directory/goo.html
은 www.naver.com이라는 컴퓨터 안에 directory 폴더 안에 goo.html이라는 파일의 위치 즉 자원의 위치를 가지고 있음으로 URL이자 URI이다.
해당 리소스의 정확한 위치정보를 포함하고 있기 때문이다.

그러나 최근들어서는 홈페이지 주소 역시 보안상, 디자인상, 유지보수상의 이유로 정확한 위치정보를 포함하지 않는경우가 많다.

http://www.naver.com/directory/132
은 directory 폴더 안에 있는 파일을 가져올 것 인데 가져올 때 식별자가 132이므로 파일을 가져오기 위해 식별자가 필요하므로 URL은 아니나 URI라고 할 수 있다.


## 그림으로 배우는 HTTP Network Basic
URI는 리소스를 식별하기 위해 문자열 전반을 나타낸다.(해당 리소스를 식별할 수 있는 식별정보)
URL은 리소스의 장소를 타나낸다.(해당 리소스의 정확한 위치정보)

[참고 !!!!](http://marlboroyw.tistory.com/280)
