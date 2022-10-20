# 04. Messaging (메세징)

## Spring Integration
스프링 기반 애플리케이션에서 경량 메시지를 사용가능하게 하고 외부 시스템을 선언적 어댑터로 쉽게 통합할 수 있는 기능을 제공한다.
https://sup2is.github.io/2020/08/12/what-is-spring-integration.html
https://springsource.tistory.com/47
https://kchanguk.tistory.com/121
https://velog.io/@daehoon12/Spring-Integration-Spring-Integration

## Spring for RabbitMQ
메세지 큐를 다룰 수 있게 해주는 메세지 솔루션.
RabbitMQ 혹은 Docker가 깔려 있어야 된다고 한다.
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
## Spring for Apache Kafka Streams
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
# 중요도: ★
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
