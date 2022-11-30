
# 15. Spring Cloud Messaging

여러 마이크로서비스들이 유기적으로 연결되어 동작하려면 신호데이터를 서로 주고받아야 한다.

이 신호데이터를 보내거나, 받거나, 이 과정을 관리하는 툴을 여기서 다룬다.

이러한 종류의 라이브러리를 메세징 브로커 등으로 불리기도 한다.




# 1) 자바 메세징 서비스 (JMS)

두 개 이상의 자바 애플리케이션이 상호 유기적으로 동작되게 하려면,

서로 손발을 맞추어 작동하기 위해서는 앱끼리 일정한 신호를 계속해서 주고받아야 한다.

이렇게 데이터를 주고받는 것을 메세징이라고 한다.

JMS는 자바로 메세징을 구현할 수 있는 서비스이다.

https://blog.outsider.ne.kr/985

https://www.youtube.com/watch?v=fxWMfouT3Kg



### 2) JMS

자바 메세징 서비스를 이용하면 앱 내부를 넘어 외부적 환경 즉,

서로 다른 여러 애플리케이션들끼리 일정한 신호를 주고받을 수 있다.

https://ko.meaniit.com/words/4694

https://ko.wikipedia.org/wiki/%EC%9E%90%EB%B0%94_%EB%A9%94%EC%8B%9C%EC%A7%80_%EC%84%9C%EB%B9%84%EC%8A%A4

https://javacan.tistory.com/entry/13



## 비동기식 메세징

메세징 서비스는 기본적으로 비동기식으로 이루어진다.

비동기식 메세징은 상대 애플리케이션의 응답을 기다리지 않고 간접적으로 메세지를 보내는 방법이다.   



## Amazon SQS

아래 라이브러리가 많이 있긴 하다만 실제로 구글로 가장 많이 검색되는 것은 AWS 관련 글들이다.

아래 것들이 AWS와 관계가 없다면 과감히 패스하고, Spring Cloud for AWS를 이용해봄직하다.

Spring Cloud Messaging과 + Amazon SQS라는 조합을 쓰게 되는데,

많은 메세지를 FIFO 즉 큐 형태로 정리하여 순차 발송하는 식으로 관리할 수 있다.

https://livebook.manning.com/book/spring-in-action-fourth-edition/chapter-17/

https://velog.io/@tjeong/Spring-Message-%EC%82%AC%EC%9A%A9%EB%B2%95

https://wordbe.tistory.com/entry/Spring-Java-Spring-%EA%B8%B0%EB%B3%B8

https://becko.tistory.com/45

https://devbada.tistory.com/10

https://uchupura.tistory.com/109

https://daddyprogrammer.org/post/14825/spring-cloud-messaging-sqs/

https://devocean.sk.com/blog/techBoardDetail.do?ID=163301

https://aws.amazon.com/ko/blogs/korea/getting-started-with-spring-boot-on-aws/

Cloud Bushttps://daddyprogrammer.org/post/14825/spring-cloud-messaging-sqs/

https://happycloud-lee.tistory.com/211



## 번외편: ActiveMQ

https://n1tjrgns.tistory.com/277



## Cloud Stream

마이크로서비스를 구축하기 위한 Spring Cloud의 라이브러리 중 중 하나로,

이벤트 중심의 마이크로서비스를 구축하기 좋으며, 경량화에 집중하였다고 한다.

pache Kafka 또는 RabbitMQ과 연동하는 방식이며,

Spring Boot 어플리케이션 간의 메세지 통신에 사용된다.

https://saramin.github.io/2019-08-28-2/

