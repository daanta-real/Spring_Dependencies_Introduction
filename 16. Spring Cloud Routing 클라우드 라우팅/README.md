

# 16. Spring Cloud Routing

API Gateway 등, 마이크로서비스 간의 "서비스 게이트웨이"

즉 서비스 클라이언트와 호출될 서비스 사이에서 중개 역할과,

어플리케이션 안의 마이크로 서비스 호출로 유입되는 모든 트래픽에 대해

게이트키퍼 역할을 할 수 있게 하기 위해 사용된다.

API 라우팅 및 보안, 모니터링/매트릭 기능 등을 구현할 수 있다.

https://geonyeongkim-development.tistory.com/72




## Gateway

기존엔 Zuul을 많이 사용하였으나, Zuul은 신규 개발이 중단되었고 

Zuul 자체가 Spring 생태계와 서로 호환이 잘 안된다고 한다.

반면 Gateway가 더 새로운 제품이고, 똑같이 비동기와 논블로킹 방식이나 환성도 성능도 더 우수하다고 한다.

현재 국내 문서를 구글링해 보면 거의 Gateway 라이브러리만 사용되는 것으로 보인다.

https://www.blog-dreamus.com/post/flo-tech-%EC%B2%AB-%EC%86%90%EB%8B%98%EC%97%90%EA%B2%8C%EB%8F%84-%EC%9E%AC%EA%B9%8D-%EC%9D%91%EB%8B%B5%ED%95%98%EA%B8%B0

https://cloud.spring.io/spring-cloud-gateway/reference/html/

https://cheese10yun.github.io/spring-cloud-gateway/

https://sky-h-kim.tistory.com/67

https://sky-h-kim.tistory.com/68

https://otrodevym.tistory.com/entry/spring-boot-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0-20-spring-cloud-gateway1-%EC%84%A4%EC%A0%95-%EB%B0%8F-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%86%8C%EC%8A%A4

https://velog.io/@dhk22/Spring-Cloud-API-Gateway-Service

https://happycloud-lee.tistory.com/218




## OpenFeign

여기는 진짜 모르겠다.

클라이언트가 REST Call을 좀더 쉽게 할 수 있도록 도와주는 라이브러리라고 한다.

https://oingdaddy.tistory.com/280

https://sharplee7.tistory.com/68

https://sharplee7.tistory.com/69?category=1045563

https://github.com/OpenFeign/feign

https://wildeveloperetrain.tistory.com/172

https://uchupura.tistory.com/90

https://techblog.woowahan.com/2630/




## Cloud LoadBalancer

### 중요도: ★

한 개 혹은 여러 서버를 이용해 서비스를 할 때, 서비스로 유입되는 트래픽이 많아 인해 부하가 유발되면

이를 효과적으로 소화해야 할 것이다.

본래 로드밸런싱의 방법에는 세 가지가 있다.

1) Scale Up: 서버의 용량을 증대시킨다.

2) Scale Out: 부하를 여러 서버에 효과적으로 분산시킨다.

3) Connection Pool (DBCP): 클라이언트들에 순번을 매겨 차례대로 트래픽을 소화한다.

로드밸런싱은, 그중 두 번째에 해당하는 기술이다.

Cloud LoadBalancer는 클라우드 서버에서 이를 적용할 수 있게 해주는 라이브러리로 보인다.

https://velog.io/@shkim1199/%EB%8C%80%EC%9A%A9%EB%9F%89-%ED%8A%B8%EB%9E%98%ED%94%BD-%ED%95%B4%EA%B2%B0

https://deveric.tistory.com/91

https://jybaek.tistory.com/843
