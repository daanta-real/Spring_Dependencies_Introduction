
# Springboot 프로젝트 설정 시 거의 필수적으로 사용되는 국룰 의존성 정리

#### 중요도: ★★★★★

이 문서에서는 Springboot 프로젝트를 생성할 때 필수적으로 사용되는 의존성에 대해서 다룬다.

세상에는 수많은 의존성들이 다른 의존성을 서브 의존성

(해당 의존성이 동작하기 위해 기본적으로 요구되는 외부 의존성)으로 두고 있다.

이 의존성들도 서브의존성들을 두고 있는데, 하나같이 거의 크리티컬한 것들로

없으면 개발 자체가 안 되는 급의 의존성들이다.

따라서 얘네에 한해 여기 별도 페이지에 정리해 보게 되었다.




## 1. Springboot Starter Web

Springboot 웹 프로젝트를 생성하려면 필수적으로 선택해야 하는 의존성이다.

이 의존성은 웹 애플리케이션을 돌리기 위한 라이브러리이다.

또한 가장 필수적이라 할 수 있는 라이브러리들을 링크하고 있어 이들을 자동으로 끌어오는데

하나같이 없으면 안 될 라이브러리들 뿐이다.

그 상세 목록은 아래와 같다.




### 1-1. Spring Core

스프링 프레임워크의 최고 핵심 코어 모듈.

이 모듈이 없으면 스프링 자체가 성립하지 않는다.

IOC(제어 반전)과 DI(의존성 주입)을 지원한다.

https://andaeng.tistory.com/65

https://workshop-6349.tistory.com/entry/Spring-Core-Spring-Core-%EC%84%A4%EB%AA%85

https://nzzi.kr/spring/%EC%8A%A4%ED%94%84%EB%A7%81-%EC%A0%9C%EC%96%B4-%EB%B0%98%EC%A0%84.html

https://outstanding1301.github.io/dev/2021/01/11/di-and-ioc/

https://velog.io/@damiano1027/Spring-%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85-%EC%A0%9C%EC%96%B4%EC%9D%98-%EC%97%AD%EC%A0%84




### 1-2. Spring Web

스프링에서 서블릿 API, 필터 등 HTTP 관련 동작 처리를 하기 위한 각종 필수적인 기능을 쓸 수 있게 해준다.

타 웹 프레임워크와 유기적으로 연동하기 위한 기능들도 지원한다.

https://stackoverflow.com/questions/13533700/maven-dependency-spring-web-vs-spring-webmvc




### 1-3. Spring Web MVC (= Spring MVC)

Spring Web만 있으면 서버가 단순히 서블릿 형태로만 굴러간다.

MVC(모델/뷰/컨트롤러) 형태로 처리하기 위해서는 이 모듈이 필요하다.

https://velog.io/@hanblueblue/%EB%B2%88%EC%97%AD-Spring2-Spring-Web-MVC

https://m.blog.naver.com/sthwin/221271008423

https://stackoverflow.com/questions/13533700/maven-dependency-spring-web-vs-spring-webmvc

https://dadadamarine.github.io/java/spring/2019/05/02/spring-MVC-%EA%B5%AC%EC%A1%B0.html




### 1-4. Springboot starter tomcat

스프링부트 내장 버전의 톰캣, 통칭 내장 톰캣 또는 임베디드 톰캣이라고 부른다.

이는 일반적인 톰캣이 아니고 스프링부트에서 돌리기 좋은 형태의 튜닝된 톰캣이라고 하는 것 같다.

일반 톰캣과는 달리 스프링에 연결할 떄 필요한 다양한 기본 설정들을 미리미리 해준다는 장점이 있다.

아래 설명 중 하나에 톰캣을 외장 톰캣으로 전환하는 방법도 기술되어 있으니 필요 시 참조하도록 하자.

https://goateedev.tistory.com/135

https://mvnrepository.com/artifact/org.springframework.boot/spring-boot-starter-tomcat

https://engkimbs.tistory.com/755




## 2. Springboot Starter Test

Springboot를 활용한 개발 중에 자신의 코드를 온갖 방법으로 테스트할 것이다.

그러한 테스트를 쉽고, 빠르고, 체계적으로 하기 위해 아래의 의존성이 추가된다.




### 2-1. JUnit

자바에서 가장 유명한 테스트 전문 프레임워크.

전체 프로젝트를 WAS를 통으로 재부팅할 필요 없이 일정한 단위만 테스트할 수 있게 해준다.

현재 4버전은 매장되는 추세이며 5버전이 국룰이다.

웬만하면 5버전을 쓰도록 하자.




### 2-2. Mockito

더미 등 목업 객체를 쉽게 만들어주는 라이브러리.

JUnit이 테스트 실행기를 만들어 준다면, Mockito는 테스트에 쓸 객체를 만들어 준다.




### 2-3. AssertJ

테스트 코드를 좀더 편리하고 쉽게 작성할 수 있도록 도와준다




### 2-4. Spring Test

JUnit에 붙여서 사용하는 파워업키트로,

JUnit의 스프링 관련 기능을 대폭 확장하여 스프링 관련된 테스트를 좀더 쉽고 빠르게

해줄 수 있도록 도와준다.

https://codevang.tistory.com/259
