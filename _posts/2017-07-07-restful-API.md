---
layout: post
title: restful API를 일반인에게 설명해보세요.
categories: Interview
tag: 면접대비, 지식
---

### Restful API의 의미
REST의 기본 원칙을 성실히 지킨 서비스 디자인은 “RESTful 하다.” 라고 흔히 표현합니다.

출처: [박상권의 삽질블로그](http://gun0912.tistory.com/63)
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
<p>위의 Json 문서에서 Resource와 URI, HTTP method를 보겠다.</p>
<ul>
  <li>Resource : "users" ~~ "mike"</li>
  <li>URI : http://myweb/users/</li>
  <li>HTTP method : POST</li>
</ul>
##### API의 의미
<p>예를 들어, 외부 사용자가 우리 회사의 프로그램의 소스 및 데이터베이스에 접근하면 안된다.</p>
<p>이런 문제를 해결하기 위해서 API가 사용된다.</p>
<ul>
  <li>1</li>
  <li>2</li>
  <li>3</li>
</ul>
