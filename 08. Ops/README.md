

# 8. Ops



## Spring Boot Actuator

### 중요도: ★★

스프링부트에서는 어플리케이션 스스로를 모니터링하고 관리하는 기능을 내장 제공하고 있다.

그 기능을 모아 놓은 의존성이 Actuator라고 한다.

이 의존성은 등록하기만 해도 각종 정보를 알려주는 엔드포인트(URL 페이지)들을 추가해 준다.

단독으로도 사용할 수 있지만, 온갖 모니터링 의존성들의 실행에 기본적으로 요구되는 의존성이라서

스프링부트를 쓴다면 그 사용 빈도가 아주 높다.

URL 페이지에 접속한다면 정보들이 http와 JMX, JSON 등으로 뜨는 걸 볼 수 있다.

※ 엔드포인트는 소통 관계에서의 한쪽 끝 즉 '접촉점'을 말하는 것이다.

앱에서는 원하는 메뉴에서의 접촉 경로라고 말할 수 있겠고, API에서는 URI라고 말할 수 있겠다.

https://sabarada.tistory.com/23

https://incheol-jung.gitbook.io/docs/study/srping-in-action-5th/chap-16.

https://supawer0728.github.io/2018/05/12/spring-actuator/

https://skagh.tistory.com/40

https://velog.io/@neptunes032/Spring-Boot-Actuator-%EC%82%AC%EC%9A%A9%ED%95%B4%EC%84%9C-%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98-%EB%AA%A8%EB%8B%88%ED%84%B0%EB%A7%81%ED%95%98%EA%B8%B0

http://forward.nhnent.com/hands-on-labs/java.spring-boot-actuator/01-ready.html

https://blog.naver.com/PostView.naver?blogId=ghdalswl77&logNo=222401162545&parentCategoryNo=&categoryNo=90&viewDate=&isShowPopularPosts=true&from=search




## codecentric's Spring Boot Admin (Client)

## codecentric's Spring Boot Admin (Server)

스프링부트로 만든 앱을 여러 개를 한꺼번에 돌릴 경우, 통합 관리자 기능을 GUI로 이용할 수 있게 해준다.

서브 앱에다가 Server 의존성을 추가하고, 메인 앱에다가 Client 의존성을 추가하면

메인 앱에서 통합 관리자 기능을 GUI로 확인 및 관리할 수 있다.

위의 Sprint Boot Actuator 기반으로 실행된다.

https://github.com/codecentric/spring-boot-admin

https://joomn11.tistory.com/68

https://jaehyun8719.github.io/2019/06/20/springboot/admin/

https://otrodevym.tistory.com/entry/spring-boot-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0-12-adminsecurity-%EC%84%A4%EC%A0%95-%EB%B0%8F-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%86%8C%EC%8A%A4

https://ynzu-dev.tistory.com/entry/Spring-Spring-Boot-Admin-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0-Log-Login-%EC%A0%81%EC%9A%A9

https://dncjf64.tistory.com/312

https://www.baeldung.com/spring-boot-admin

https://jinn-blog.tistory.com/74

https://www.tutorialspoint.com/spring_boot/spring_boot_admin_server.htm
