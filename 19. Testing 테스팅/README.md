
# 19. Testing

개발 중 다양한 테스트를 돕기 위한 툴들이 여기에 모여 있는 것 같다.

마이크로서비스 아키텍처를 테스트하는 방법 중 처음에 오는 다섯 가지를 기재해 놓으므로

이를 참고하면 좋을 것이다.




1. 단위 테스트

내가 테스트하길 원하는 단위만 골라서 테스트한다.

메소드 단위만 할 수도 있고 조금 넓은 범위의 시스템을 테스트할 수도 있다.



2. 컴포넌트 테스트

단위테스트 이후에 실시하며,

외부시스템과 연결을 끊어놓고 마이크로서비스 내부전체를 테스트한다.

격리된 상태에서 테스트를 하기 위해서 가상(Mock / Stub) 구조를 만들어 테스트한다.




3. 통합 테스트

INPUT에서 OUTPUT까지 전체 단위를 테스트한다.

REQUEST를 받는 시점부터 내부의 작동, 중간에 실행되는 외부와의 연결까지 한꺼번에 테스트한다.

컴포넌트 테스트와 똑같지만, 컴포넌트 테스트에서는 외부와 실제 연결을 하지 않지만

통합 테스트에서는 외부와 실제로 통신을 한다.




4. Contratct Test

본 Contract Verifier 라이브러리가 하는 것이 이것이다.

마이크로서비스의 API "연결(Contract) 구조"가 정확히 되어있는지 테스트할 때 사용하는 것으로,

서비스 간의 메세징 혹은 API 구조가 개발자가 예상한 대로 잘 정의되어 있는지, 잘 작동하는지 검증해 준다.

모든 서비스를 테스트하는 게 아니고, 내 마이크로서비스만 테스트하므로

다른 마이크로서비스나 외부서비스는 미지의 상태(=블랙박스 상태)로 가정하고 테스트한다.




5. End to End 테스트

나의 내부시스템을 외부 시스템과 연결하려 할 때,

외부 시스템의 다양한 요구사항들을 만족해서 실행하는지를 검사한다.

시스템 내외부에 연관된 모든 것들을 한 번에 테스트하기 떄문에 테스트에 주의를 기울여야 한다.

https://juneyr.dev/2018-10-11/test-in-spring

https://kouzie.github.io/spring/%EC%8A%A4%ED%94%84%EB%A7%81-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EB%A7%88%EC%9D%B4%ED%81%AC%EB%A1%9C%EC%84%9C%EB%B9%84%EC%8A%A4-%ED%85%8C%EC%8A%A4%ED%8A%B8/



## Spring REST Docs

사이트에서 사용되는 API들에 대한 명세서를 보고 싶다면?

설명서를 만들 수 있는 도구가 여럿 있다.

가장 유명한 건 Swagger지만, 유료라고 알고 있고

명세서에 설명을 잘 써넣기 위해 코드에 어노테이션을 덕지덕지 붙여야 한다는 단점이 있다.

반면 Spring REST Docs는 테스트가 성공해야만 해당 항목의 문서가 만들어지며

어노테이션의 추가 없이 명세가 생성된다는 장점이 있다.

그만큼 사용법이 어려운 것이 아쉽다고 한다. 

https://tecoble.techcourse.co.kr/post/2020-08-18-spring-rest-docs/



## Testcontainers

개발 중 테스트 환경을 위한 DBMS 셋팅을 도와준다.

테스트 때에만 컨테이너를 올렸다가 테스트가 끝나면 셋팅을 내리는 식이다. 

https://velog.io/@lsb156/Spring-Boot-TestContainers

https://medium.com/riiid-teamblog-kr/testcontainer-%EB%A1%9C-%EB%A9%B1%EB%93%B1%EC%84%B1%EC%9E%88%EB%8A%94-integration-test-%ED%99%98%EA%B2%BD-%EA%B5%AC%EC%B6%95%ED%95%98%EA%B8%B0-4a6287551a31

https://taes-k.github.io/2021/05/02/spring-test-container/

https://dealicious-inc.github.io/2022/01/10/test-containers.html



# Contract Verifier

마이크로서비스의 API 연결(Contract) 구조가 정확히 되어있는지 테스트할 때 사용하는 것으로,

서비스 간의 메세징 혹은 API 구조가 개발자가 예상한 대로 정의되어 있는지 검증해 준다.

특징으로는 모든 서비스를 테스트하는 게 아니라 연결 그 자체만 테스트한다는 것이다.

상대방의 서비스를 블랙박스로 가정하여 테스트한다.

https://velog.io/@csh0034/Spring-Cloud-Contract

https://ko.quish.tv/consumer-driven-contract-testing-with-spring-cloud-contract



# Contract Stub Runner

JUnit은 자바나 스프링, 스프링부트 등 모든 자바 프로그램에서 내가 원하는 범위의 내용을 테스트할 수 있는 툴이다.

JUnit의 확장 라이브러리에는 다양한 종류가 있다.

JUnit의 어노테이션 기능에는 한계가 크다. 체이닝도 안 돼서 읽기도 힘들고

IDE가 자동완성을 지원하지 않기도 한다.

이럴 때 AssertJ는 확장 라이브러리를 사용하면,

내가 작성한 테스트코드의 가독성이 올라가고, 테스트도 더 편하고 쉽게 할 수 있게 된다.

또한, Test Double(스턴트맨을 의미하는 용어) 계열의 확장 라이브러리가 있다.

이는 실제 환경과 유사한 셋팅을 아예 가짜로 만들어서 거기서 테스트하게 함으로써

실제 환경을 건드리지 않고도 실제에 준하는 수준으로 검증할 수 있게 해준다.

스프링에서의 Test Double 검증 방식은 크게 5개로 이루어진다.

1) Dummy

가짜 객체를 만들어만 줌. 내용은 테스트하기 힘들고 객체 유무 그 자체만 검증하고자 할 때.

어떤 코드는 다른 객체가 있어야 동작하는 경우가 있는데 이때 검사를 통과하기 위해 특정 더미를 만드는 식.

2) Stub

가짜 객체 생성 + 최소한의 기능 구성. 객체의 기본적인 동작 등, 그 상태를 검증하고자 할 때.

메소드의 로직이 없고 결과만 있다. 요청을 받으면 반사적으로 정해진 값 or 상태만 반환하는 식.

3) Spy

가짜 객체 생성 + 최소한의 기능 구성 + 객체 관련된 로그 등 약간의 정보 기록. 동작 수준을 확인하고자 할 때

4) Fake

가짜 객체 생성 + 최소한의 기능 구성 + 진짜의 동작을 따라한 유사 기능까지 구현.

객체+기능+동작 전부 재현. 진짜와 거의 똑같고 다만 데이터 등이 가짜인 경우.

거의 완전한 수준에서의 테스트를 할 수 있다.

이중에서 Stub Runner는, Contract(서비스 간의 연결) 상황에서의 Stub(객체+필수기능)까지 생성해주는 라이브러리인 것 같다.

### Stub vs Mock

둘코드 작성 자체는 쉽지만 이를 위해서 불필요한 전용 코드를 또 만들어야 하므로 시간이 낭비될 수 있고

상태를 항상 가정하므로 값의 변경을 테스트할 수 없는 한계가 있다.

경우에 따라 아싸리 Mocking Test로 가는 것이 더 좋을 수도 있음. 어차피 Mock이 최종 형태이므로.

https://juneyr.dev/2018-10-11/test-in-spring

https://bibi6666667.tistory.com/231

https://choibulldog.tistory.com/67

https://jiwondev.tistory.com/186

https://jiwondev.tistory.com/184

https://giron.tistory.com/104

https://small-stap.tistory.com/m/94

https://small-stap.tistory.com/92

https://velog.io/@new_wisdom/assertJ-%EA%B3%B5%EC%8B%9D%EB%AC%B8%EC%84%9C%EC%99%80-%ED%95%A8%EA%BB%98%ED%95%98%EB%8A%94-assertJ-%EC%A0%95%EB%A6%AC

https://juneyr.dev/2018-10-11/test-in-spring

https://tecoble.techcourse.co.kr/post/2020-09-19-what-is-test-double/

https://dev-kidult.tistory.com/15

https://cloud.spring.io/spring-cloud-contract/1.2.x/multi/multi__spring_cloud_contract_stub_runner.html

https://velog.io/@new_wisdom/assertJ-%EA%B3%B5%EC%8B%9D%EB%AC%B8%EC%84%9C%EC%99%80-%ED%95%A8%EA%BB%98%ED%95%98%EB%8A%94-assertJ-%EC%A0%95%EB%A6%AC




# Embedded LDAP Server

### Jobkorea 검색건수: 15건

임베디드: 범용이 아니라 딱 특정 목적으로만 굴리기 위한 장비를 말한다.

LDAP(Lightweight Directory Access Protocol): 디렉토리 서비스를 제공하기 위한 프로토콜이다.

네트워크상에서 조직이나 개인, 파일, 디바이스 등을 찾아볼 수 있게 해준다.

즉 스프링의 Embedded LDAP Server란,

네트워크 상에서 디렉토링 서비스를 제공할 목적으로 굴리는 전용 서버를 만들어줄 수 있게 해주는 프레임워크이다.

구글에 찾아보니 스프링으로 임베디드 LDAP 서버를 생성하면 보통 로그인이나 기타 보안 관련된 업무를 시키는 것 같다.

https://www.samsungsds.com/kr/insights/ldap.html

https://shanepark.tistory.com/303

https://spring.io/guides/gs/authenticating-ldap/

https://asbnotebook.com/spring-boot-embedded-ldap-example/




# Embedded MongoDB Database

임베디드 기기에서 MongoDB DBMS 서버를 돌릴 수 있게 해주는 것 같다.

https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=scw0531&logNo=221068794003

https://velog.io/@coffiter/MongoDB-Spring-Boot-Embedded-MongoDB-%EC%97%B0%EA%B2%B0

https://kogle.tistory.com/293
