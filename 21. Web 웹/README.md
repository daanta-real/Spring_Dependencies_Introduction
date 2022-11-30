
# 21. Web

본 카테고리에선 웹 서버를 도와주기 위한 API 및 다양한 파워업키트 툴을 제공한다.

API란, 서비스와 서비스 간의 통신을 위해 사전에 약속한 규격대로 만들어진 다양한 인터페이스를 총칭한다.

본래 이 분야의 최고존엄은 SOAP(1999)라는 방식의 API였는데,

이것이 몹시 불편해서 새로 나온 것이 REST API(2000)이고, 는 SOAP를 순식간에 대체하여 세계 최고의 API방식이 되었다.

RESTful(2000)에 단점이 아주 없진 않다.

RESTful API는 사전에 정해둔 옵션으로만 요청할 수 있으므로 

다양한 옵션을 유동적으로 지원해야 하는 API라면

요청을 한 번만 해서는 안 되고, 작은 단위 요청을 여러 번 날려야 되는 불편함이 있다.

그럼에도 불구하고 논리적으로 가장 다루기 편하여 개발 및 유지보수 효율이 압도적으로 높다는 장점 때문에,

다양한 대체 규격이 제안되어 오고 있음에도 불구하고 현재도 RESTful 규격이 가장 많이 쓰이고 있다.

https://namocom.tistory.com/666

https://bangu4.tistory.com/167




## Spring Web
웹 서비스라는 기능 즉,
멀티파일 업로드, 서블릿 리스너 등을 지원하고 HTTP 클라이언트를 지원하며
Spring MVC 패턴을 이용할 수 있게 지원해주고
톰캣과의 연결까지 지원한다고 한다.
스프링의 모든 의존성 중에서 가장 중요한 핵심 프레임워크이다.
이것이 없으면 스프링 앱 자체가 성립될 수 없다. 
https://dev-setung.tistory.com/26
https://mvnrepository.com/artifact/org.springframework/spring-web
https://appleg1226.tistory.com/11

## Spring Reactive Web
본래 Reactive는 Spring에서 만든 개념이 아니지만,
어쨌든 Spring 5버전부터는 Reactive를 구현하기 위한
Spring Reactive 프로그래밍이라는 것을 지원하기 시작했다.
이 라이브러리를 이용하면, Reactive Stream을 이용한
Reactive 웹프로그래밍을 지원하는 웹앱을 만들 수 있다.
Reactive라는 것은 "차단하지 않는"다는 것을 의미하는데,
원래 요청을 받으면 응답을 되돌려준 후 통신을 차단하지만,
Reactive에서는 차단을 하지 않는 개념이어서
이가 적용되면 클라이언트에서는 서버 측이 작업이 완료되었거나
혹은 데이터가 준비되었을 때까지 기다릴 수 있고,
이후 알림까지도 실시간으로 받아볼 수 있게 된다.
Reactive는 Spring MVC 구조와 병용할 수 있는데,
Reactive Stack 영역을 생성하고,
그 안의 요청은 Spring MVC가 Spring Webflux로 대체되는 식이다. 
Spring Reactive는, Reactive Stream의 구현체인
Reactor를 기반으로 한 Webflux가 담겨 있으므로,
다른 말로 Webflux라고 부르기도 한다. 참고.
https://taes-k.github.io/2019/05/21/about-spring-reactive/
https://wedul.site/570

## Spring for GraphQL
RESTful API 규격의 단점을 보완하기 위해
지금까지 다양한 방식의 API 규격이 제안되었는데,
그중 그나마 핫한 방식이 GraphQL(2015)이다.
RESTful API에서는 사전에 정해진 단위의 요청만 날릴 수 있었지만,
이 GraphQL은 "내가 필요한 쿼리들을 선택해서 한 번에 날릴 수 있다"
라는 큰 장점이 있어 새로운 방식의 API로 주목을 받아왔다.
하지만, 장점이 크지만 단점도 큰 방식이다.
어떤 실무자들은 GraphQL이 기존 방식보다 복잡해져 불편하다고 한다.
(이를테면 정해진 내용의 통신만 계속 하는 API라면
다양한 옵션을 지원하는 GraphQL의 성능이 RESTful보다 훨씬 떨어질 것이다)
유용함에 대한 의견이 분분하다.
호오가 많이 갈리는 기술이다. 난 배울 계획이 없다.
https://spring.io/projects/spring-graphql
https://kotlinworld.com/330
https://www.redhat.com/ko/topics/api/what-is-graphql
https://siyoon210.tistory.com/153

## Rest Repositories
## Rest Repositories HAL Explorer
Spring Data는 Spring 프로젝트 중 데이터의 접근을 쉽게 도와주는 프로젝트이다.
DBMS로의 접근은 수많은 상용적인 쿼리 코드들에 주요 구문을 붙여서 만든 쿼리로 이루어진다.
이 Spring Data 프로젝트의 주요 목표는, 그러한 쿼리 코드 구조를 줄여줌으로써
쿼리 관련된 코드 작성의 효율을 높여주는 것이다. 
대표적인 것으로 Spring Data JPA라는 것이 있다.
그리고 Rest Repositories 프로젝트는,
Spring Data 프로젝트에서 생성되는 Repository(영속성 저장소?라는 것 같다)
들을 Rest API를 통해 접근할 수 있게 해주는 응용모듈이라고 한다.
Spring Cloud급으로 많이 어려운 개념이므로 나중에 공부하는 것이 좋겠다.
https://blog.jiniworld.me/127 
https://data-make.tistory.com/621
https://engkimbs.tistory.com/823
https://escapefromcoding.tistory.com/377
https://appleg1226.tistory.com/11
https://arahansa.github.io/docs_spring/jpa.html

## Spring Session
MSA 구조에서는 수많은 서버들이 얽혀 유기적으로 동작하게 되는데,
HTTP 세션이라는 것은 항상 각 서버 단위로만 저장되므로,
이를 연계하는 과정에서 서버 간 세션 정보가 차이가 나게 된다.
Spring Session은 이런 상황에서 여러 서버들의 세션을
쉽게 동기화할 수 있도록 도와주는 라이브러리이다.
https://scshim.tistory.com/447
https://thecodinglog.github.io/spring-session/2020/08/07/filter-chain.html
https://spring.io/projects/spring-session

### Spring HATEOAS
REST API의 규약 중에는 "어플리케이션 상태에 대한 엔진으로써 하이퍼미디어"
즉 HATEOAS(Hypermedia As The Engine Of Application State)
라는 규약이 있으며, 이는 REST API의 필수 구성요소 중 하나이다.
사용자가 리소스를 얻기 위해 API를 호출하였을 때, 목표한 리소스 뿐만 아니라
해당 리소스와 관련된 다양한 곁다리 링크 정보들을 데이터에 첨부시켜서
리소스와 관련링크(Content-Type=application/"hal"+json)를
함께 묶어 보냄으로써, 서버가 클라이언트에게 하이퍼미디어(링크 등)을 통해
정보를 동적으로 제공하는 규약이 HATEOAS이다.
https://spring.io/projects/spring-hateoas
https://engkimbs.tistory.com/866
https://haruhiism.tistory.com/200
https://brunch.co.kr/@purpledev/29
https://velog.io/@bluewind8791/Spring-HATEOAS
https://www.baeldung.com/spring-hateoas-tutorial
https://bamdule.tistory.com/247

## Spring Web Services
SOAP 규격의 API를 구현할 수 있게 해주는 의존성이다.
위에서 SOAP는 지금은 쓰지 않는 deprecated된 방식이라고 하였으므로
이것은 평생 쓸 일 없을 것 같다. 
Spring Web은 웹 서버를 구현하는 근본 프레임워크이고,
Spring Web Service는 SOAP API용 툴킷이다.
둘이 전혀 다른 의존성이다. 절대로 착각하지 말 것!!
https://namocom.tistory.com/666
https://spring.io/projects/spring-ws
https://godekdls.github.io/Spring%20Boot/web-services/
https://appleg1226.tistory.com/11?category=864243

## Jersey
자바 개발진들이 공식적으로 제공하는 REST API 라이브러리이다.
스프링과는 아무 상관 없는 라이브러리이며,
현재 스프링 및 스프링부트에서는 이게 없어도
Controller가 있기 때문에 REST API를 개발할 수 있기 때문에,
스프링 프레임워크를 적용하지 않는 환경에서 웹서비스를 구현하고 싶거나
레거시 프로젝트를 건드려야 하는 경우가 아니면 이 라이브러리를 접할 일은 없다.
https://velog.io/@hanblueblue/Jersey-Jersey-2.0%EC%9C%BC%EB%A1%9C-%EA%B0%9C%EB%B0%9C%ED%95%98%EB%8A%94-RESTful-%EC%9B%B9-%EC%84%9C%EB%B9%84%EC%8A%A4
https://blog.jiniworld.me/162
https://mrtint.tistory.com/755
https://pmingdiary.tistory.com/9
https://digitalbourgeois.tistory.com/56
https://coding-plant.tistory.com/16
※ Spring WebClient, Okhttp, Jersey 셋 간의 차이를 모르겠다.

## Vaadin
Java 기반 웹UI 프레임워크라고 한다.
HTML, Javascript, CSS 아무 것도 몰라도
전용 Java 코드만 알면 웹 UI를 그릴 수 있게 해준다고 한다.
근데 현재 프론트엔드/백엔드에 다양한 템플릿들이 다수 나와 있는 데다가,
각각의 기능도 엄청나게 강력해서 이게 필요 없으며,
애초에 백엔드 담당은 프론트 안 건드리고 백엔드 영역만 하는 데다가
자바 프로그램을 개발할 때 Java GUI를 쓰지 굳이 웹UI를 쓸 리가 없다.
해서 지금도 앞으로도 이걸 쓸 일은 없을 거라고 확신함.