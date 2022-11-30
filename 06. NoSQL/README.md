
# 6. NoSQL

데이터를 안정적으로 저장하기 위해 등장한 RDBMS는 한 개의 테이블을 한 개의 데이터베이스 서버에서만 다룰 수 있다.

21세기에 들어 웹이 등장하며 데이터베이스를 활용한 서비스의 규모는 점점 커져 갔으며

이로 인해 테이블 하나하나가 엄청나게 커지게 되었고, 결국 비용이 기하급수적으로 늘어나 감당이 안 되는 사태가 벌어진다.

이를 해결하기 위해 데이터의 저장에 SQL 외의 구조 혹은 SQL을 아예 안 사용하는 구조를 찾는 사람들이 늘어났고

데이터를 표로 취급해서 관리하는 SQL 형식이 아닌,

클러스터 구조(혹은 클라우드)로 여러 서버에 분산 저장하도록 한 DBMS들이 나오게 되었다.

대부분은 21세기 초에 개발되었고, 오픈소스이며, SQL을 사용하지 않기 떄문에

사람들은 이들을 'Not Only SQL(SQL만 쓰지는 않음)'이란 뜻의 NoSQL이라고 불렀다.

('NO SQL(SQL이 아님)'이란 뜻이 아니다. SQL 외의 요소를 주로 사용한단 뜻이다. 주의)

참고로 RDBMS가 떠오르기 전에 등장한 기존 1,2,3세대 구형 DBMS는 NoSQL로 쳐주지 않는다.

현재의 NoSQL의 개발 목적과 전혀 다른 목적으로 나온 애들이기 때문.

NoSQL을 쓸 때에는 단점을 정확히 인지하고 주의해서 사용하여야 한다.

대부분 속도를 위해 ACID 트랜잭션(한 단위 작업이 끝나기 전에는 다른 모든 작업이 중지됨)을 포기했으므로

RDBMS와는 달리 데이터의 안정성이 보장되지 않는다.

NoSQL 데이터베이스의 유형은 Key-value형 / Document형 / Column-family형 / Graph형 등이 있으며

이중 Graph형을 제외한 나머지 세 개는 집합-지향(Aggregate-oriented) 모델이다.

NoSQL 데이터베이스에서 유명한 것들은 Redis(Jobkorea 432건), MongoDB(311건), Elasticsearch(242건), Firebase(198건) 정도이다.




## Spring Data Redis (Access+Driver)

### 중요도: ★★★

### Jobkorea 검색건수: 432건

데이터를 보조기억장치(디스크)가 아닌 주기억장치(메인메모리) 즉 RAM에 저장하는 NoSQL이다.

In-Memory Database(IMDB), 혹은 MMDB(Main Memory DBMS)라고도 하는데,

응답 속도가 엄청나게 빠르지만, 매체가 휘발성이므로 서버를 끄면 모든 데이터가 날라가는 단점이 있다.

따라서 가급적이면 단기간 갖고 있을 데이터, 날아가도 상관 없는 데이터 위주 다루게 되며,

장기 저장이 필요한 데이터를 다룰 경우, 보조기억장치 쪽으로 주기적인 백업을 하는 식으로 쓴다.

상급 개발자로 활동하려면 이 데이터베이스의 사용법을 무조건 알고 있어야 한다.

https://namu.wiki/w/%EC%9D%B8%20%EB%A9%94%EB%AA%A8%EB%A6%AC%20%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4




## Spring Data Reactive Redis

## Reactive Redis

### 중요도: ★

Spring Framework 5에서 Reactive(=Web Flux) 프로그래밍이 가능하였다고 한다. 

https://taes-k.github.io/2019/05/21/about-spring-reactive/

https://incheol-jung.gitbook.io/docs/q-and-a/spring/spring-5

그리고 Redis를 Reactive하게 쓸 수 있게 해주는 것이 이 의존성이라고.

Spring Reactive 자체가 새로운 기술이기 때문에 시장 반영이 상당히 느리게 될 것이다.

이건 솔직히 쓸지 안 쓸지도 잘 모르겠다. 서둘러 배우지 않아도 된다고 생각한다.

https://daddyprogrammer.org/post/4056/reactive-redis/

https://www.oss.kr/storage/app/public/festival/track2/2-1.pdf

https://wellbell.tistory.com/238

https://programmer-chocho.tistory.com/75

https://pearlluck.tistory.com/727




## Spring Data MongoDB

### 중요도: ★★

### Jobkorea 검색건수: 311건

데이터를 문서(document) 형태로 저장하는 NoSQL이다.

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

Ring 구조로 작동하는 분산형 인메모리 NoSQL DBMS로 높은 확장성과 고가용성을 자랑한다고.

스프링 4.x + MyBatis를 쓰고 있다면 갈아탈 생각을 해봐도 좋다고 한다.

https://kyle79.tistory.com/14

https://spring.io/projects/spring-data-cassandra

http://wiki.hash.kr/index.php/%EC%B9%B4%EC%82%B0%EB%93%9C%EB%9D%BC

https://bourbonkk.tistory.com/83

하지만 성능평가 논문을 보면 Redis나 MongoDB에 비해 눈물이 나올 수준으로 느리다.

논문을 보면 HBase라는 DBMS도 보이는데 이것도 성능이 별로다.

http://blessldk.blogspot.com/2013/02/redis-vs-cassandra-1.html

http://www.koreascience.or.kr/article/JAKO201621650894999.pdf




# Spring Data Reactive For Apache Cassandra

Apache Cassandra를 쓸 때 Reactive하게 쓸 수 있게 해준다고 한다.

https://hantsy.github.io/spring-reactive-sample/data/data-cassandra.html




## Spring for Apache Geode

Apache Geode는 인메모리 DBMS로 데이터를 key-value 형태로 저장 관리한다고 한다.

그 Apache Geode를 스프링에서 쓸 수 있게 하는 툴인가 보다.

Gemfire라는 녀석의 오픈소스 백엔드라고 하는데, 둘이 무슨 관계지?

뭐가 됐건 Redis를 쓰면 되는 상황에 굳이 이걸 쓸 필요가 없다.

https://zetawiki.com/wiki/%EC%95%84%ED%8C%8C%EC%B9%98_Geode

https://tanzu.vmware.com/developer/data/tanzu-gemfire/guides/spring-for-apache-geode/

https://docs.spring.io/spring-boot-data-geode-build/1.4.x/reference/html5/




## Spring Data Couchbase

카우치베이스 서버라고 한댄다. Redis 같은 인메모리 NoSQL중 하나이다.

역시 Redis가 있어서 필요 없다.

https://bcho.tistory.com/924

https://victorydntmd.tistory.com/349

https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=tmondev&logNo=221016955783

https://javadoc.io/doc/org.springframework.data/spring-data-couchbase/latest/index.html

https://hantsy.github.io/spring-reactive-sample/data/data-couchbase.html

https://www.baeldung.com/spring-data-couchbase




## Spring Data Reactive Couchbase

Couchbase를 쓸 때 Reactive하게 쓸 수 있게 해주는 녀석 같다..




## Spring Data Neo4j

노드와 이에 해당하는 연산 사이의 종속관계를 쉽게 다룰 수 있게 하는 DBMS라고 함.

https://wordbe.tistory.com/entry/Spring-Data-Neo4j-%EC%82%AC%EC%9A%A9




## ※ 번외편: MongoDB

### 중요도: ★★

### Jobkorea 검색건수: 293건

MongoDB가 MariaDB보다 핫하다.

https://forteleaf.blogspot.com/2016/06/db-vs-db.html

https://velog.io/@cmong/MongoDB-vs-MySQL-vs-SQLite3-%EB%AD%98%EC%93%B0%EC%A7%80
