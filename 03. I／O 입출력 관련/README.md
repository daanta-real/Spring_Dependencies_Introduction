# 03. I/O (입출력 관련)

## Spring Batch
### 중요도: ★★★
로깅/추적, 트랜잭션 관리, 작업 처리 통계, 작업 재시작, 건너뛰기, 리소스 관리 등
대용량 레코드 처리에 필수적인 기능을 제공한다고 한다.
대부분의 프로젝트에서는 주기적인 자동화 처리 작업이 필요하며
그 경우 이 의존성이 반드시 있어야 한다.
https://khj93.tistory.com/entry/Spring-Batch%EB%9E%80-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B3%A0-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0

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
실습은 Gmail로 했었다.
https://victorydntmd.tistory.com/342
https://theheydaze.tistory.com/255

## Quartz Scheduler
### 중요도: ★★★
특정 코드에 대한 예약 실행 관리를 할 때 쓰인다.
CRON 문자열을 이용하여 스케쥴링을 할 수 있다.
스케쥴링을 하기 위해 Batch와 함께 필수적인 의존성이므로
웬만한 프로젝트는 두 의존성을 모두 사용하고 있다.
https://byul91oh.tistory.com/275

## Spring cache abstraction
### 중요도: ★
앱 내부에서 자주 사용되는 코드를 캐싱하여 실행속도를 높일 수 있도록 관리해 주는 라이브러리.
@Cacheable 어노테이션을 사용한다고.
https://12bme.tistory.com/550

## Picocli
GraalVM 지원 명령줄 앱을 쉽게 구축하기 위한 최신 라이브러리이자 프레임워크..라고 하는데.
Java CLI 명령행 애플리케이션 제작 라이브러리 라고 한다.
그러니까 자바로 간단한 앱을 제작할 때 쓰면 될 것 같은데. 코틀린도 되려나?
(CLI는 Command Line Application이라고 하는데,
윈도의 명령 프롬프트 같은 걸 기반으로 텍스트 기반 UI의 앱을 일컫는다고 보면 된다.)
http://taewan.kim/post/position_of_graalvm/
https://kwonnam.pe.kr/wiki/java/picocli
http://jason-heo.github.io/programming/2021/08/28/jbang.html

## Spring Shell
스프링 프로그래밍 모델을 기반으로 손쉽게 커맨드라인 애플리케이션(interactive shell)을 만들 수 있도록 도와주는 프로젝트
Picocli랑 비슷한가 싶다.
https://javaworld.co.kr/67
http://www.incodom.kr/Spring_Shell
