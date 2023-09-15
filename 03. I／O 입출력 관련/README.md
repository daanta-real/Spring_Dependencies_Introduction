
# 03. I/O (입출력 관련)

## Spring Batch

### 중요도: ★★★

로깅/추적, 트랜잭션 관리, 작업 처리 통계, 작업 재시작, 건너뛰기, 리소스 관리 등

대용량 레코드 처리에 필수적인 기능을 제공한다고 한다.

대부분의 프로젝트에서는 주기적인 자동화 처리 작업이 필요하며

그 경우 이 의존성이 반드시 있어야 한다.

https://khj93.tistory.com/entry/Spring-Batch%EB%9E%80-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B3%A0-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0

## Quartz Scheduler

### 중요도: ★★★

특정 코드에 대한 예약 실행 관리를 할 때 쓰인다.

CRON 문자열을 이용하여 스케쥴링을 할 수 있다.

스케쥴링을 하기 위해 Batch와 함께 필수적인 의존성이므로

웬만한 프로젝트는 두 의존성 중 하나 or 둘 다 사용하고 있다.

https://byul91oh.tistory.com/275




## Spring Batch, Quartz Schedler 둘 다 똑같은 의존성 아닌가?

틀린 말이다. 둘 다 기본적인 스케쥴링 작업을 지원하나, 엄연히 다른 의존성이다.

Batch는 DBMS를 활용한 스케쥴링, 대용량 배치 처리 기능 등을 지원하여

방대한 작업을 세밀하게 셋팅할 수 있는 Batch Job 중심의 라이브러리

즉 작업 하나를 잘 하는 라이브러리이고 

Quartz는 여러 스케쥴러 인스턴트 들의 클러스터링이 가능한

Job Management 중심 즉 작업들을 잘 관리하는 라이브러리이다.

따라서 보통 스케쥴링을 제대로 하는 프로젝트에서는,

Spring Batch와 Quartz Scheduler를 함께 사용한다고 한다.

Batch로 작업을 만들고 이를 Quartz로 묶어서 하는 식으로.

https://www.stechstar.com/user/zbxe/JSPWebProg/51097

https://hyejikim.tistory.com/67

https://yongku.tistory.com/m/entry/%EC%8A%A4%ED%94%84%EB%A7%81-%EB%B0%B0%EC%B9%98Spring-Batch%EC%99%80-Quartz

https://stackoverflow.com/questions/4385719/spring-scheduling-scheduled-vs-quartz



## 참고로 스프링 환경에서 스케쥴링 기능을 쓰는 방법은 대표적으로 4가지이다.

1) Servlet-Context.xml에 Cron Namespace와 BEAN 등록

   XML에 스케쥴링을 등록하는 방법이다.
   
   스프링부트에서는 2번 방법을 쓰면 편하게 스케쥴링할 수 있는데,
   
   이 방법은 너무 옛날 방식이다. 따라서 쓰이지 않는다.

2) 스프링 내장 @Scheduled 어노테이션

   학원에서 배운 것이 이것이다.

   최소한의 기본 기능만 있는 수준이고 정밀도가 엄청나게 높은 편은 아니어서,

   사용 수준이 아마추어 레벨에 가깝다.

   그러나, 간단한 작업만 필요할 경우에는 이것만으로도 충분하다고 판단된다.

   Spring Boot에서 제대로 사용하려면 Application 클래스에 @EnableScheduling

   어노테이션을 붙여 사용하면 된다.

3) Quartz Scheduler + Spring Batch

   정밀도가 아주 높다. 간단한 작업이 아닌 이상 여기를 쓰는 것이 좋다.

   복잡한 작업이면 여기 외에는 선택지가 없다.

4) Jenkins 등의 CI/CD 툴 별도 이용

   배포관리나 스케쥴링, 통합 테스트 등의 자동화는 여기를 쓰는 것이 좋다.

   그러나, 이건 앱 내부에서 쓸 수 있는 툴이 아니다.
   
   앱의 빌드와 배포, 테스트 관리 등 앱 외부적인 '환경' 관련된 작업만

   관리할 수 있는 툴이다.

   그러니까 1/2/3과 관련이 없는 툴이란 거다.

가장 좋은 방법은 3이다.

앱에서는 Quartz를 쓰고, 관련된 파이프라인 작업은 Jenkins를 쓰자.

https://veneas.tistory.com/entry/Spring-Boot-%EC%8A%A4%ED%94%84%EB%A7%81-%EC%8A%A4%EC%BC%80%EC%A4%84-%EC%9E%91%EC%97%85-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0EnableScheduling-Scheduled

https://wooncloud.tistory.com/m/75



## Validation

### 중요도: ★★★

서버로 입출력되는 데이터를 검증하기 위해 사용하는 라이브러리.

클래스 필드의 최대값, 최소값, Nullable 여부 등을 이 의존성이 담당한다고 한다.

DB 사용 시 쿼리가 뻑나지 않게 하려면 이 기능을 넣는 것을 강력하게 추천한다.

물론 실무에서 적용이 쉽진 않을 것이지만,

데이터 무결성을 보장하려면 원칙적으로 최소한 이것을 넣어보려고는 해야 한다.

@Valid 어노테이션으로 작동한다고.

https://velog.io/@_koiil/SpringBoot-Spring-Validation%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EC%9C%A0%ED%9A%A8%EC%84%B1-%EA%B2%80%EC%A6%9D

https://wildeveloperetrain.tistory.com/25




## Java Mail Sender

### 중요도: ★★

Spring으로 메일 송수신 등의 메일서비스(주로 Gmail) 이용할 수 있게 해주는 라이브러리이다.

전에 실습할 때 기억으로는 의존성에 들어가는 메일서비스마다

사용법도 다르고 규격이 다르다고 했던 것 같다.

실습할 땐 Gmail로 했었다.

https://victorydntmd.tistory.com/342

https://theheydaze.tistory.com/255




## Spring cache abstraction

### 중요도: ★★

앱 내부에서 자주 사용되는 코드를 캐싱하여 실행속도를 높일 수 있도록 관리해 주는 라이브러리.

@Cacheable 어노테이션을 사용한다고 한다.

이 의존성은 스프링에 내장된 모듈이라고 하는데, 플젝 생성 시 웬만해선 있을 것 같다.

하지만 Redis 같은 DB를 물려서 제대로 쓰려면 해당 소프트들은 따로 설치를 해줘야 한다고 한다.    

https://12bme.tistory.com/550




## Picocli

GraalVM 지원 명령줄 앱을 쉽게 구축하기 위한 최신 라이브러리이자 프레임워크..라고 하는데.

Java CLI 명령행 애플리케이션 제작 라이브러리 라고 한다.

그러니까 자바로 간단한 앱을 제작할 때 쓰면 될 것 같은데.

코틀린도 되려나? 잔디체커도 이걸로 기능을 확장할 수 있을까?

(CLI는 Command Line Application이라고 하는데,

윈도의 명령 프롬프트 같은 걸 기반으로 텍스트 기반 UI의 앱을 일컫는다고 보면 된다.)

배포할 때에는 JReleaser를 이용한다고.

http://taewan.kim/post/position_of_graalvm/

https://kwonnam.pe.kr/wiki/java/picocli

http://jason-heo.github.io/programming/2021/08/28/jbang.html




## Spring Shell

스프링 프로그래밍 모델을 기반으로 손쉽게 커맨드라인 애플리케이션(interactive shell)을

만들 수 있도록 도와주는 프로젝트. Picocli랑 비슷한 라이브러리로 추정.

CLI 어플리케이션을 제공하는 이런 Shell 기반의 프로그램들에선

사용자가 명령을 입력해서 원하는 기능을 실행할 수 있다고 한다.

(CLI Application ≒ Shell Application ≒ Interactive Shell Application 약간 비슷한 건가 보네)

https://javaworld.co.kr/67

http://www.incodom.kr/Spring_Shell
