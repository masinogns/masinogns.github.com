---
layout: post
title: restful API를 일반인에게 설명해보세요.
categories: Interview
tag: 기술면접, 지식, API
---
### 의문 ? 웹의 본래 설계의 우수성
무엇이 있을까?

### Restful API의 의미
REST의 기본 원칙을 성실히 지킨 서비스 디자인은 “RESTful 하다.” 라고 흔히 표현합니다.

출처: [박상권의 삽질블로그](http://gun0912.tistory.com/63)

REST 아키텍처 스타일에 따라 정의되고 이용되는 서비스나 응용프로그램을 RESTful 웹 서비스라고 부름.

<p>자원 지향 아키텍처(Resource Oriented Architecture) ROA</p>
<p>RESTful의 경우 리소스를 등록하고 저장해두고는 중간 매개체가 없어 리소스 제공자가 *직접* 리소스 요청자에게 제공한다.</p>
<p>RESTful 웹 서비스는 인터넷 서비스업체들이 응용 개발자들에게 손쉬운 *데이터 제공* 목적으로 출발했다.</p>
<p>RESTful 웹서비스는 기계보다는 사람이 이해 하기 쉽도록 인터넷 기본(HTTP/XML)이외에 별도의 개발/실행 환경이 필요 없음.</p>
출처 : [Slied Share](https://www.slideshare.net/seunghochoi4/soap-restful)
### Rest 의미와 구성
##### REST의 의미
REST = *R*epresentational *S*tate *Transfer*

##### REST의 구성
REST = Resource 20% + URI 70% + HTTP method 10% !!
```
HTTP  POST, http://myweb/users/
{
  "users":{
    "name": "mike"
  }
}
```
<p>url는 무엇인가?</p>
<p>HTTP method는 무엇인가?</p>
<p>위의 Json 문서에서 Resource와 URI, HTTP method를 보겠다.</p>
<ul>
  <li>Resource : "users" ~~ "mike"</li>
  <li>URI : http://myweb/users/</li>
  <li>HTTP method : POST</li>
</ul>

##### REST의 동작 원리
기본 HTTP 프로토콜의 메소드 GET/PUT/POST/DELETE를 이용하여 서비스 제공자에게 서비스를 요청.
서비스 제공자는 다양한 형태로 표현된 (JSON, XML, RSS 등) 리소스를 반환
<p>HTTP request, respose 비교 이해 필요</p>
출처 : [Slide Share 2](https://www.slideshare.net/yjaeseok/soap-rest)
##### API의 의미
<p>예를 들어, 외부 사용자가 우리 회사의 프로그램의 소스 및 데이터베이스에 접근하면 안된다.</p>
<p>이런 문제를 해결하기 위해서 API가 사용된다.</p>


```
URI : dogs/1
1) Content-Type: application/json
2) Content-Type: application/xml
3) Content-Type: application/png
```
Content-Type에 대해서 명시하여 원하는 리소스를 선택할 수 있으므로 URI 내에는 파일 확장자를 포함하지 않는 것이 좋습니다.

```
dogs/1.xml

위와 같은 URI를 만드는 것보다,

dogs/1

위의 URI에 Content-Type: application/xml헤더를 포함하여 요청을 보내는 것이 더 적절한 선택입니다.
```
 확장자를 달리하여 같은 리소스에 대한 다른 표현 양식을 주문하는 것이지 해당 리소스가 달라지는 것은 아닙니다. 또한, URI에 직접 확장자가 붙게 되면 해당 리소스 URI가 응답으로 지원하는 확장자만큼 새로운 URI들이 생기게 되겠지요. 결코, 이것은 좋은 디자인이 아닙니다.

 기본으로 GET, PUT, POST, DELETE 요청에 1:1매치 되는 개념인 CRUD가 있습니다. CRUD의 앞글자들을 풀어보면 Create, Read, Update, Delete가 될 텐데, 각각 POST, GET, PUT, DELETE에 대응되는 개념입니다. 그런데 사실 URI를 디자인 하다 보면 이러한 방식으로 나타내기 참 어려운 경우를 많이 만나게 됩니다. 그 중 가장 많은 경우가 어떤 특정한 행위를 요청하는 경우입니다. 많은 분이 이럴 때 동사를 쓰는데, 앞선 포스팅에서 밝혔듯이 동사를 써서 URI를 디자인하는 것은 대체로 옳지 않은 방식으로 여겨집니다.
이럴 때 컨트롤러 리소스를 정의하여 이 문제를 해결할 수 있습니다. 컨트롤러 리소스는 URI 경로의 제일 마지막 부분에 동사의 형태로 표시되어 해당 URI를 통해 접근했을 때 일어날 행위를 생성합니다. (개념적으로는 이렇게 받아들이시면 됩니다.) 생성과 관련된 요청이 POST이기 때문에 컨트롤러 리소스에 접근하려면 POST 요청을 보내야 합니다.

### 중심 규칙
REST에서 가장 중요하며 기본적인 규칙은 아래 두 가지입니다.
URI는 정보의 자원을 표현해야 한다.
자원에 대한 행위는 HTTP Method(GET, POST, PUT, DELETE 등)으로 표현한다.
1번 사용자에 대해 정보를 받아야 할 때를 예를 들면, 아래와 같은 방법은 좋지 않습니다.
GET /users/show/1
이와 같은 URI 방식은 REST를 제대로 적용하지 않은 구 버전의 Rails에서 흔히 볼 수 있는 URL입니다. 이 URI은 자원을 표현해야 하는 URI에 /show/ 같은 불필요한 표현이 들어가 있기 때문에 적절하지 않습니다. 본다는 것은 GET이라는 HTTP Method로 충분히 표현할 수 있기 때문이죠. 최근의 Rails는 아래와 같이 변경되었습니다.
GET /users/1
자원은 크게 Collection과 Element로 나누어 표현할 수 있으며, 아래 테이블에 기초한다면 서버 대부분과의 통신 행태를 표현할 수 있습니다.

```
1) URI는 정보의 자원을 표현해야 한다. (리소스명은 동사보다는 명사를 사용)
    GET /members/delete/1
위와 같은 방식은 REST를 제대로 적용하지 않은 URI입니다. URI는 자원을 표현하는데 중점을 두어야 합니다. delete와 같은 행위에 대한 표현이 들어가서는 안됩니다.

2) 자원에 대한 행위는 HTTP Method(GET, POST, PUT, DELETE 등)로 표현
위의 잘못 된 URI를 HTTP Method를 통해 수정해 보면

    DELETE /members/1
으로 수정할 수 있겠습니다.
회원정보를 가져올 때는 GET, 회원 추가 시의 행위를 표현하고자 할 때는 POST METHOD를 사용하여 표현합니다.

회원정보를 가져오는 URI

    GET /members/show/1     (x)
    GET /members/1          (o)
회원을 추가할 때

    GET /members/insert/2 (x)  - GET 메서드는 리소스 생성에 맞지 않습니다.
    POST /members/2       (o)

```
출처 : [toast](http://meetup.toast.com/posts/92)

### in Rails
Rails 에선 기본적인 CRUD를 제공할 때 아래와 같은 REST 인터페이스를 구성해줍니다.
HTTP Verb	Path	action	used for
GET	/photos	index	display a list of all photos
GET	/photos/new	new	return an HTML form for creating a new photo
POST	/photos	create	create a new photo
GET	/photos/:id	show	display a specific photo
GET	/photos/:id/edit	edit	return an HTML form for editing a photo
PUT	/photos/:id	update	update a specific photo
DELETE	/photos/:id	destroy	delete a specific photo

### ...
REST는 HTTP와 XML을 이용하여 데이터를 주고 받는 웹 서비스를 이용하는 것으로 쓰이고 있습니다.
<p>일반적인 웹 서비스가 SOAP 인것인가?</p>
출처:  [하루에 하나씩.....](http://kimseunghyun76.tistory.com/18)
