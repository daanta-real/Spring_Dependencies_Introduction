# I/O (입출력 관련)

## Spring Batch
로깅/추적, 트랜잭션 관리, 작업 처리 통계, 작업 재시작, 건너뛰기, 리소스 관리 등 대용량 레코드 처리에 필수적인 기능을 제공한다고 한다.
https://khj93.tistory.com/entry/Spring-Batch%EB%9E%80-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B3%A0-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0

## Validation
서버로 입출력되는 데이터를 검증하기 위해 사용하는 라이브러리. 
@Valid 어노테이션으로 작동한다고.
https://velog.io/@_koiil/SpringBoot-Spring-Validation%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EC%9C%A0%ED%9A%A8%EC%84%B1-%EA%B2%80%EC%A6%9D
https://wildeveloperetrain.tistory.com/25

## Java Mail Sender
Spring으로 메일 송수신 등의 메일서비스(주로 Gmail) 이용할 수 있게 해주는 라이브러리.
https://victorydntmd.tistory.com/342
https://theheydaze.tistory.com/255

## Quartz Scheduler
특정 코드에 대한 예약 실행 관리를 할 때 쓰인다.
CRON 문자열을 이용하여 스케쥴링을 할 수 있다.
https://byul91oh.tistory.com/275

## Spring cache abstraction
앱 내부에서 자주 사용되는 코드를 캐싱하여 실행속도를 높일 수 있도록 관리해 주는 라이브러리.
@Cacheable 어노테이션을 사용한다고.
https://12bme.tistory.com/550

## Picocli
GraalVM 지원 명령줄 앱을 쉽게 구축하기 위한 최신 라이브러리이자 프레임워크..라고 하는데
Java CLI 명령행 애플리케이션 제작 라이브러리 라고 한다.
http://taewan.kim/post/position_of_graalvm/
https://kwonnam.pe.kr/wiki/java/picocli
http://jason-heo.github.io/programming/2021/08/28/jbang.html

## Spring Shell
스프링 프로그래밍 모델을 기반으로 손쉽게 커맨드라인 애플리케이션(interactive shell)을 만들 수 있도록 도와주는 프로젝트
Picocli랑 비슷한가 싶다.
https://javaworld.co.kr/67
http://www.incodom.kr/Spring_Shell