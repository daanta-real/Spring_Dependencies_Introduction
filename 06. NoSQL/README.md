
# 6. NoSQL



## Spring Data Redis (Access+Driver)

### 중요도: ★★★

### Jobkorea 검색건수: 440건

In-Memory Database(IMDB), 혹은 MMDB(Main Memory DBMS)라고도 하며

DB의 저장을 보조기억장치(디스크)가 아닌 주기억장치(메인메모리)에 맡기는 DB이다.

응답 속도가 엄청나게 빠르지만, 매체가 휘발성이므로 서버를 끄면 모든 데이터가 날라가는 단점이 있다.

따라서 가급적이면 단기간 갖고 있을 데이터, 날아가도 상관 없는 데이터 위주 다루게 되며,

장기 저장이 필요한 데이터를 다룰 경우, 보조기억장치에 주기적인 백업을 하게 된다.

이 데이터베이스는 상급 되려면 거의 필수적으로 알고 있어야 한다.

https://namu.wiki/w/%EC%9D%B8%20%EB%A9%94%EB%AA%A8%EB%A6%AC%20%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4



## Spring Data Reactive Redis

## Reactive Redis

### 중요도: ★

Spring Framework 5에서 Reactive(=Web Flux) 프로그래밍이 가능하였다고 한다. 

https://taes-k.github.io/2019/05/21/about-spring-reactive/

https://incheol-jung.gitbook.io/docs/q-and-a/spring/spring-5

그리고 Redis를 Reactive하게 쓸 수 있게 해주는 것이 이 의존성이라고.

Spring Reactive 자체가 새로운 기술이기 때문에 시장 반영이 상당히 느리게 될 것이다.

서둘러 배우지 않아도 된다고 생각한다.

https://daddyprogrammer.org/post/4056/reactive-redis/

https://www.oss.kr/storage/app/public/festival/track2/2-1.pdf

https://wellbell.tistory.com/238

https://programmer-chocho.tistory.com/75

https://pearlluck.tistory.com/727



## Spring Data MongoDB

### 중요도: ★

### Jobkorea 검색건수: 311건

데이터를 문서(document) 형태로 저장하는 NoSQL.

그중 대표적인 DB인 MongoDB를 스프링에서 사용할 수 있게 해주는 의존성이다.

https://secretartbook.tistory.com/4

https://luvstudy.tistory.com/62



## Spring Data Reactive MongoDB

꽤 인기 있는 DBMS인 MongoDB를 reactive 모드로 쓸 수 있게 해주는 의존성.

https://luvstudy.tistory.com/58



## Spring Data Elasticsearch (Access+Driver)

### 중요도: ★★

### Jobkorea 검색건수: 246건

Apache Lucene 상에서 돌아가는, 자바 기반의 오픈소스 RESTful 검색/분석 엔진이라고.

모든 타입의 데이터를 처리할 수 있는 것이 특징인데, 데이터를 JSON 문서로 저장하기 때문이라고 한다.

https://tecoble.techcourse.co.kr/post/2021-10-19-elasticsearch/



## Spring Data for Apache Cassandra

### Jobkorea 검색건수: 20건

분산형 데이터베이스? NoSQL이라고 한다.

속도가 빠르다고?

스프링 4.x + MyBatis를 쓰고 있다면 갈아탈 생각을 해봐도 좋다고.

근데 이미 Redis가 있으므로 굳이 이걸 쓸 일이 많은가 싶다.

https://kyle79.tistory.com/14

https://spring.io/projects/spring-data-cassandra

Spring Data Reactive For Apache Cassandra
Apache Cassandra를 쓸 때 Reactive하게 쓸 수 있게 해준다고 한다.
https://hantsy.github.io/spring-reactive-sample/data/data-cassandra.html



## Spring for Apache Geode
Apache Geode는 인메모리 DBMS로 데이터를 key-value 형태로 저장 관리한다고 한다.
그 Apache Geode를 스프링에서 쓸 수 있게 하는 툴인가 보다.
Gemfire라는 녀석의 오픈소스 백엔드라고 하는데, 둘이 무슨 관계지?
https://zetawiki.com/wiki/%EC%95%84%ED%8C%8C%EC%B9%98_Geode 
https://tanzu.vmware.com/developer/data/tanzu-gemfire/guides/spring-for-apache-geode/
https://docs.spring.io/spring-boot-data-geode-build/1.4.x/reference/html5/



## Spring Data Couchbase
카우치베이스 서버라고 한댄다.
인메모리 NoSQL중 하나이다.
갠적으론 인지도 면에서 MongoDB를 쓰는 게 더 좋을 듯.
https://bcho.tistory.com/924
https://victorydntmd.tistory.com/349
https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=tmondev&logNo=221016955783
https://javadoc.io/doc/org.springframework.data/spring-data-couchbase/latest/index.html
https://hantsy.github.io/spring-reactive-sample/data/data-couchbase.html
https://www.baeldung.com/spring-data-couchbase

※ Cassandra라는 DBMS도 있다고 함.
Ring 구조로 작동하는 분산형 인메모리 NoSQL DBMS로 높은 확장성과 고가용성을 자랑한다고.
http://wiki.hash.kr/index.php/%EC%B9%B4%EC%82%B0%EB%93%9C%EB%9D%BC
https://bourbonkk.tistory.com/83



## Spring Data Reactive Couchbase
Couchbase를 쓸 때 Reactive하게 쓸 수 있게 해주는 녀석 같다..



## Spring Data Neo4j
노드와 이에 해당하는 연산 사이의 종속관계를 쉽게 다룰 수 있게 하는 DBMS라고 함.
https://wordbe.tistory.com/entry/Spring-Data-Neo4j-%EC%82%AC%EC%9A%A9