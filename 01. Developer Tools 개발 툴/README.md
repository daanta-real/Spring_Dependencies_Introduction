
# 01. Developer Tools (개발 툴)



## Spring Native [Experimental]

기존의 자바 프로그램은, JAR(단일앱 일반), WAR(웹서버 용), EAR(여러 앱 모음) 등이 있으며

이를 구동하려면 JVM(Java Virtual Machine) 이라는 프로그램이 필요하다.

https://ifuwanna.tistory.com/224

이를 대체하는 Spring Native라는 의존성은 JVM이 전혀 필요 없는 독립 실행파일을 릴리즈할 수 있도록 해준다. 

https://wylee-developer.tistory.com/49

https://tyrannocoding.tistory.com/57



## Spring Boot DevTools

### 중요도: ★★★

Spring에서 제공하는 개발 편의를 위한 모듈이다.

수정된 소스를 테스트하기 위해서는 해당 코드로 재빌드를 거쳐야 하는데,

이걸 기다리는데 걸리는 시간이 만만치 않다.

본 의존성에서 Live Reload라는 걸 쓰게 되면 소스를 빠르게 자동으로 재빌드해 주므로

쓸 수 있는 환경에서 반드시 써야 한다.

https://barbera.tistory.com/47



## Lombok

### 중요도: ★★★

자바 클래스에서 필수적으로 쓰는 Getter, Setter, toString부터 시작해서

Hashcode, Constructor, Builder, NonNull 등..

온갖 어노테이션을 이용해 가지각색의 셋팅과 관련기능을 알아서 붙여 주는 의존성이다.

자바에서 가장 많이 쓰는 의존성 중의 하나로, 이것이 없다면 개발이 몹시 불편해져서

질 낮은 SI 업체에서 다른 스택은 뭐가 뭔지 몰라도 Lombok만큼은 자유자재로 다룰 줄 알 정도이다.

서버에 최초 설치할 때 IDE 밖에서 전용파일을 통해 설치를 한 번 해줘야 한다.

(Eclipse 기준이라서 IntelliJ에서는 다를 수 있음)

가장 자주 볼 수 있는 어노테이션은 웬만한 어노테이션들을 모두 합쳐놓은 @Data 어노테이션이다.

https://dololak.tistory.com/783



## Spring Configuration Processor

### 중요도: ★★

이게 있으면 별 셋팅을 하지 않아도 앱 구동과 동시에

application.yml 혹은 properties*.* 파일의 내용을 자동으로 읽어와 멤버변수에 할당해 준다.

그러니까 프로퍼티 읽어와 주는 의존성이다.

이클립스에서는 큰 셋팅이 필요 없는 것 같은데,

IntelliJ에서는 Annotaion Processor와 Spring Assistant를 켜야 동작한다는 듯.

한편 스프링과 스프링부트 둘 다 쓸 수 있는지는 따로 확인해봐야 할 것 같다.

참고로 클래스 안에서 설정값을 만들어 붙이려면 @ConfigurationProperties 어노테이션을 쓰면 된다고.   

https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=vefe&logNo=222065703815

https://velog.io/@bey1548/spring-boot-configuration-processor

https://perfectacle.github.io/2021/11/21/spring-boot-configuration-processor/
