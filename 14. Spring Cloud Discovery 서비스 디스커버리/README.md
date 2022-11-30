

# 14. Spring Cloud Discovery

분산 애플리케이션 서비스의 관리를 위한 라이브러리다.

분산클라우드 서비스 중에는 다양한 이벤트로 인해 서버의 정보가 변경되는 일이 잦다.

Failover(장애극복)으로 개별 IP가 변경되는 일도 있고, Auto Scaling 등의 동작으로 신규 서버가 동적으로 생성되는 일도 있고,

배포를 새롭게 하는 과정에서 IP가 변경되는 일도 있다.

이렇게 마이크로서비스 아키텍처 내 IP나 포트 정보가 변경되면 이 위치를 중앙에서 파악하여 등록/관리할 수 있게 한다.

또한 부하에 따라 서버 인스턴스를 생성/삭제하는 Load Balancing 작업을 자동으로 해주는 기능도 겸비한 것 같다.

이를 Service Discovery라고 부른다.

(또는 Cloud Service Discovery, Dynamic Service Discovery, 조정 서비스) 

구현 방식은 크게 클라이언트측과 서버측으로 나뉘어 있다고 한다.

https://jangcenter.tistory.com/32




## Fail Tolerence, Failover, Data Skew

1) Fail Tolerence (=Fault Tolerence; 장애감내, 실패감내) vs Failover (장애극복, 실패극복)

Fail Tolerence(즉시복구): 서버가 경고 없이 멈췄을 때 운영이 끊기지 않도록 시스템을 즉시 복구해 주는 것

Failover(바꿔치기): 여러 마이크로서비스를 돌릴 때 문제가 있는 서비스가 발견하면 알아서 끄고

비상용 서버로 교체함으로써, 전체 앱의 서비스에 지장이 생길 만한 상황을 방지해 주는 것

[Fail Tolerence는 즉시복구, Failover는 바꿔치기]

2) Data Skew (데이터 쏠림)

DBMS에서 데이터 분산이 자원에 분배되지 못해서 특정 데이터가 한 자원 안에 지나치게 쏠려 있는 것을 말한다.

이렇게 되면 성능이 나빠지므로 쿼리를 개선하든가 구조를 뜯어고쳐야 한다.

https://www.computerbusinessresearch.com/Home/enterprise-architecture/failover-and-fault-tolerant/

https://docs.aws.amazon.com/ko_kr/redshift/latest/dg/diagnostic-queries-for-query-tuning.html#identify-tables-with-data-skew-or-unsorted-rows

https://m.blog.naver.com/aim4u/222139745602




## 번외편: kubernetes

### 중요도: ★★★

### Jobkorea 검색건수: 494건

https://kubernetes.io/ko/docs/concepts/overview/what-is-kubernetes/



## 번외편: Eureka, Zookeeper, Kubernetes, Consul 비교글

https://stackoverflow.com/questions/48635782/what-is-the-role-of-zookeeper-vs-eureka-for-microservices



## Eureka Discovery Client

## Eureka Server

검색결과가 가장 많은 녀석이다.

라이브러리가 클라이언트측과 서버 측으로 나뉘어 있다.

https://jangcenter.tistory.com/32

https://mangchhe.github.io/springcloud/2021/04/07/ServiceDiscoveryConcept/

https://freedeveloper.tistory.com/437

https://happycloud-lee.tistory.com/210

https://authentication.tistory.com/24

https://sarc.io/index.php/cloud/1634-eureka

https://www.haedongg.net/?p=153

https://www.haedongg.net/?p=164



## Apache Zookeeper Discovery

https://sinna94.tistory.com/entry/ZooKeeper-%EC%99%80-Spring-Cloud-ZooKeeper

https://kubernetes.io/ko/docs/tutorials/stateful-application/zookeeper/

https://ko.wikipedia.org/wiki/%EC%95%84%ED%8C%8C%EC%B9%98_%EC%A3%BC%ED%82%A4%ED%8D%BC



## Cloud Foundry Discovery

여러 마이크로서비스들을 빠르게 실행/동작 관리하며 상호의존성으로 생기는 문제를 해결해 준다.

https://kerberosj.tistory.com/230

https://develop-yyg.tistory.com/4



## Consul Discovery

각 마이크로서비스의 검색, 구성 및 분할 기능을 갖춘 컨트롤 플레인을 제공한다.

전체 서비스 메쉬를 쉽게 구축할 수 있게 해준다고 한다.

왠지 대규모 서비스에서 쓰일 것 같다..

https://yaboong.github.io/spring-cloud/2018/11/25/spring-cloud-config/

https://sarc.io/index.php/cloud/1601-about-consul

