# 04. Messaging (메시징)

소규모를 넘어 중규모 서비스만 되어도,
한 개의 플젝만으로 모든 필요한 기능이 구현되지 못할 때가 많아
여러 플젝들을 만들고 그들끼리 데이터를 주고받게 하는 식으로 제작하게 된다.
이떄 서로 다른 규격으로 통신을 하게 되면 양측 간의 데이터가 제대로 전달되지 않을 것이므로
데이터 내용과, 통신 방법 등 다양한 규격을 맞추게 된다.
데이터 내용에 대한 규격을 프로토콜이라고 하며 대해서는 여기서 다루지 않는다.
연결 방식에 대한 규격에는 API, 메세징 등이 있다.

API와 메세징에는 차이가 있다.
API는 목표 앱에 요청(Request)을 넣어 응답(Response)을 받아내기 위한
앱과 앱 간의 1:1 '개인' 통신 규격이다.
요청을 받는 동시에 응답을 보내주는, 동기식 동작을 하며
만약에 응답을 즉시 받지 못할 경우 응답 정보는 손실될 수 있다.

반면 메세징은 다수의 연결이 한 앱에 중첩된 n:1:n 상황에서
그들 간의 안정적인 데이터 전달, 부하 분산, 보안 처리 등을 하기 위한 '중개' 통신 규격이다.
요청을 던져 놓으면 특정 이벤트 때(혹은 순번이 돌아왔을 때) 응답을 보내주는, 비동기식 동작을 한다.
응답을 즉시 받지 못하더라도 언젠가 적합한 시점에 그 데이터를 온전히 받아낼 보장이 있다.

API와 메세징은 둘 다 특징과 장단점이 있어서 상황에 맞게 써야 한다. 
여기서는 메세징 관련된 의존성들을 소개한다.
https://developer.ibm.com/articles/introduction-apis-and-messaging/

## Spring Integration
### 중요도: ★
스프링 기반 애플리케이션에서 경량 메시지를 사용가능하게 하고 외부 시스템을 선언적 어댑터로 쉽게 통합할 수 있는 기능을 제공한다.
https://sup2is.github.io/2020/08/12/what-is-spring-integration.html
https://springsource.tistory.com/47
https://kchanguk.tistory.com/121
https://velog.io/@daehoon12/Spring-Integration-Spring-Integration

## Spring for RabbitMQ
### 중요도: ★★★
메세지 큐를 다룰 수 있게 해주는 메세지 솔루션.
publish/consume 기능을 아주 쉽게 구현할 수 있게 도와준다.
메세징을 다룬다면 필수 의존성이다.
RabbitMQ 혹은 Docker가 깔려 있어야 된다고 한다.
학습할 때에는,
Spring Message > JMS(-APIR) > AMQP > RabbitMQ > Spring for RabbitMQ 순으로 학습할 것.
https://itchallenger.tistory.com/342
https://ojt90902.tistory.com/670
https://velog.io/@tjeong/Spring-Message-%EC%82%AC%EC%9A%A9%EB%B2%95
https://augustines.tistory.com/183
https://augustines.tistory.com/184
https://dev-gorany.tistory.com/324
https://primayy.tistory.com/76
https://velog.io/@armton/Docker-Springboot-RabbitMQ-%EC%B4%88%EA%B0%84%EB%8B%A8-%EC%97%B0%EB%8F%99
https://intrepidgeeks.com/tutorial/using-rabbit-mq-in-spring-guide

## Spring for Apache Kafka
Spring for Apache Kafka Streams
### 중요도: ★★★
데이터 이동에 쓰는 스트림들을 실시간으로 관리하고 보내기 위한 분산 스트리밍 플랫폼인 Kafka를 스프링에서 쓸 수 있게 해주는 기능.
https://blog.naver.com/arkdata/222632637775
https://www.redhat.com/ko/topics/integration/what-is-apache-kafka

## Spring for Apache ActiveMQ 5
가장 대중적이고 강력한 오픈 소스 메세징 그리고 통합 패턴 서버.
JMS랑 연관 있는 듯
https://swiftymind.tistory.com/9

## Spring for Apache ActiveMQ Artemis
Java로 작성된 무료 멀티 프로토콜 Java 기반 메시지 브로커 소프트웨어이다.
응용 프로그램 간 통신을 허용하는 산업 표준 프로토콜을 지원한다.
https://yorublog.tistory.com/46

## WebSocket
(주로 SockJS, socket.io 등과 병행 활용하여) 채팅방 등의 메세지 전문 서버를 만들 수 있게 해준다.
socket.io가 정말 많이 쓰인다고 한다.
https://dev-gorany.tistory.com/212

    원래 HTTP 통신을 할 때에는 특징이 있었다.
    전송을 마치면 연결을 끊어버리며(=비연결성), 접속상태를 자체적으로 저장하지 않는다(=무상태)
    문에 채팅방처럼 실시간으로 지속적인 연결을 해야 하는 경우 연결 및 관리가 힘들었다.
    접속을 반복적으로 하는 데서 오는 피로를 줄이고 응답속도 저하를 줄여준다.
    
    이를 개선하여 웹소켓이라는 프로토콜(규격)이 나왔는데,
    웹소켓에서는 연결상태를 관리하고 실시간으로 연결을 유지하는 방식이 되어서
    관리가 중요한
    https://victorydntmd.tistory.com/286
    상태WebSocket은 프로토콜 https://www.educba.com/websocket-vs-socket-io/

https://dev-gorany.tistory.com/212

## RSocket
TCP, WebSocket, 그외에 다른 바이트 스트림 전송을 통해 다중화된 이중 통신 응용 프로그램 프로토콜.
https://araikuma.tistory.com/847

## Apache Camel
"시스템 통합"이란 걸 잘 하게 만드는? 자바 프레임워크라고 함.
미들웨어용 메세징 관리 소프트웨어라는데..
https://miiingo.tistory.com/200
https://bcho.tistory.com/715
https://www.youtube.com/watch?v=Zwq8bxHnwqg

## Solace Pubsub+
실시간 기업을 위한 통합 event 스트리밍 및 관리 플랫폼.
종합적인 이벤트 관리 플랫폼..이라는데
https://solace.com/ko/products/platform/
