
# 9. SQL

SQL(Structured Query Language; 구조적 질의 언어)는 데이터베이스에서 자료를 처리하고

원하는 결과를 얻기 위해 입력하는 특수 목적용 언어이다.

이 메뉴에서는 데이터베이스 및 관계형 DBMS(RDBMS) 의존성들을 다루고 있다.




## 주의!

이 파트에서는 JDBC/JDA 의존성들의 이름이 거의 똑같다. 그러나 서로 다른 의존성들이므로, 구분에 유의해야 한다.

### 1. 발전 순서

출시 순서를 무시하고 기술의 발전 순서 별로 정렬하면 아래와 같다.

JDBC(1997) > Spring JDBC(=JdbcTemplate, 2005) > MyBatis(iBatis 시절 기준 2002) > JPA인터페이스(2006) 혹은 Hibernate(2001)

### 2. 현황

순서 상 가장 발전된 것은 JPA 계열이지만 다루기가 대단히 어렵고 러닝커브도 매우 가파르다.

초 대규모 프로젝트가 아닌 이상 이것이 투머치라는 인식이 많아서, 대부분 MyBatis를 쓴다.

### 3. 자세한 설명 참조

- JDBC > Spring JDBC > MyBatis 순 정리:

https://blog.neonkid.xyz/223

- JDBC > Spring JDBC > JPA 순 정리:

https://katfun.tistory.com/entry/Spring-%EC%8A%A4%ED%94%84%EB%A7%81%EC%9D%98-DB-%EC%A0%91%EA%B7%BC-%EA%B8%B0%EC%88%A0-%EA%B0%84%EB%8B%A8-%EC%86%8C%EA%B0%9C

### 4. 각종 SQL 의존성 차이점 정리 (중요! 혼동 X)

JDBC = 자바로 DBMS 접속하는 원천 "라이브러리"
       자바 진영이 직접 만들었다.

JDBC API = JDBC를 스프링에서 이용하기 위해 만든 스프링용 JDBC 의존성

Spring JDBC = JDBC API를 코드 길이를 줄여서 편하게 쓰기 위해 나온 개선판

JPA = 자바에서 RDBMS 접근을 쿼리 한 줄 없이 객체만으로 할 수 있도록 그 골격만 잡은 "인터페이스(껍데기)".
      
      아무런 코드가 없고 순 interface랑 Enum만 줄줄이 적어 놓은 기술 명세이다.
      
      소스를 열어 보면 마치 매미 허물마냥 단 한 줄의 코드도 없다.
      
      자바 진영이 직접 만들었다.

Hibernate = 위 JPA 규격을 실제로 구현한 구현체이다. JPA를 실제로 구현한 의존성 중에서 가장 유명하다.
      
            (사실 JPA의 구현체는 Hibernate 말고도 많이 있지만 Hibernate를 제외하고 전부 성숙하지 못했고,
      
            실제로는 Hibernate만 쓰게 되었다.
      
            시간이 지나다 보니 사람들은 JPA 하면 Hibernate밖에 생각하지 못하게 됐고,
      
            이 때문에 JPA = Hibernate인 줄로 잘못 착각하는 나 같은 사람이 생기게 되었다.)

Spring Data = 스프링에서는 각 데이터베이스에 좀더 쉽게 접근할 수 있도록
      
              데이터베이스와 상관 없이 똑같은 형태의 추상화 객체를 제공하려 한다.
      
              스프링 쓸 때는 데이터베이스를 신경쓰지 말고 스프링에서 주는 객체를 신경 쓰라는 이야기이다.
      
              DB 별로 한 개씩 시리즈가 있다. Spring Data JPA, Spring Data MongoDB, Spring Data Redis 등등..
      
              만약에 이걸 잘 쓸 줄 안다면 각종 DB를 비슷한 개면의 추상화 객체로 동시에 잘 다룰 수 있을 것이다.
              
https://brunch.co.kr/@springboot/107

Spring Data JPA = Spring Data 시리즈 중 JPA에 해당하는 의존성이다.
              
                  Hibernate 자체는 쌩 JPA이며 무척 어렵다. 이를 스프링에서 공통 모듈 형태로 쓰게 하려고 있는 의존성이다.
              
                  Hibernate 자체를 한 단계 더 추상화시켜 전용 객체를 제공하고,
              
                  사용자는 그 전용 객체만 쓰면 Hibernate가 어떻게 돌아가는지 신경쓸 필요 없이 JPA를 쓸 수 있게 된다.

Spring Data JDBC = 위의 JPA

(Spring JPA = ← ← ← 이거는 존재하지 않는 표현이다. 가끔 블로그에서 Spring Data JPA를 이걸로 부르던데 틀린 표현이다.)

https://suhwan.dev/2019/02/24/jpa-vs-hibernate-vs-spring-data-jpa/




## JDBC API

"JDBC(Java DataBase Connector)"는 DBMS에 접근할 수 있게 하기 위해서

<u><b>자바가 직접<u><b> 제공하는 인터페이스이다.

그리고 스프링에서 이를 쓰게 해주기 위해 이 JDBC API 의존성이 존재한다.

자바에서의 모든 DMBS 의존성은 이 API를 사용한다. MyBatis도 Hibernate도 내부에선 JDBC 형태로 동작한다.

그러니 JDBC API는 DBMS 접근의 근간이라고 할 수 있다.

다만, JDBC(자바에선 JDBC, 스프링에선 JDBC API) 그 자체는 20년도 넘은 라이브러리라서 직접 실행하려면 굉장히 불편하다.

쿼리 한 줄 날리려고 써야 하는 코드가 굉장히 복잡하다. 커넥션을 직접 열고 닫아야 하고, ResultSet을 관리해야 하는 등등..

20년 전에나 직접 썼지 지금은 편의성 개선을 위해 좋은 라이브러리가 많이 나와 있어서 직접 쓰는 일은 없다.

그냥 있다는 것 정도만 알자.




#### "JDBC를" 자바에서 직접 쓰기

https://db2helmet.tistory.com/66 

https://jwkim96.tistory.com/98




#### JDBC를 실행하는 의존성인 "JDBC API"를 스프링에서 쓰기

https://gmlwjd9405.github.io/2018/05/15/setting-for-db-programming.html




#### 번외편: Spring JDBC

스프링에서 JDBC API를 편리하게 사용하기 위해 만든 JDBC API의 개선판이다.

JDBC를 실행하는 과정에서 생기는 각종 잡코드를 WRAPPING한 <u><b>JdbcTemplate<u><b>라는 객체를 만들었으며,

사용자에게는 XML로 의존성을 주입한 다음 이 객체만 불러 DBMS에 접근할 수 있게 하도록 함으로써 코드량을 줄였다.

JDBC의 복잡한 커넥션 절차가 간소해져서 좀더 MyBatis에 가까운 모습을 보여주지만,

쿼리는 여전히 String을 직접 넣어서 날린다. 이는 쿼리와 코드가 여전히 분리가 안 됐다는 얘기인데,

한 클래스 안에 비즈니스 로직과 DB 처리 로직이 섞이게 되므로 단일 책임 원칙이 깨진다는 단점이 있어서

대체제가 많은 지금까지 쓰고 있는 사람은 없다.

그냥 있다는 것 정도만 알자.

https://gmlwjd9405.github.io/2018/05/15/setting-for-db-programming.html

https://bibi6666667.tistory.com/300

https://soongjamm.tistory.com/134




## Spring Data JPA

### 중요도: ★★★

### Jobkorea 검색건수: 69건 (Hibernate)


프로그래밍 언어를 써서 코드로 DBMS에 접근할 때,

관련 코드를 빠르게 개발하고 안정적인 구동을 보장해주는 프레임워크를 퍼시스턴스 프레임워크라고 한다.

퍼시스턴스 프레임워크는 두 종류이다.

MyBatis 같이 SQL 문장을 직접 작성하여 다루는 SQL Helper 즉 "SQL Mapper",

그리고 SQL을 직접 다루지 않고 객체로 취급하여 이 객체를 만들어 SQL을 간접적으로 다루는

"ORM(Object Relational Mapping)"이다.

기존 Helper는 SQL을 직접 편집했지만, ORM에서는 쿼리 작성 없이 객체만 작성하여 쿼리를 날리므로

데이터베이스를 다룰 때 데이터베이스 설계를 안 하고 객체 설계를 하여 다루게 된다.

ORM 의존성은 JPA와 Hibernate 두 가지 키워드로 말할 수 있다.

첫째, JPA는 자바 진영의 ORM 기술의 표준 의존성인데, 구현체이다.

즉 아무 코드가 없고 단순 interface하고 Enum 등만 득실득실한 껍데기이다.

때문에 JPA를 쓰려면 결국 누군가의 객체로 구현해서 써야 한다.

둘째, 이중 Hibernate는 가장 많이 사용하는 의존성이다.

다행히도 Spring Data JPA 의존성을 주입하면, Hibernate Core 의존성이 종속 의존성으로 자동으로 딸려 오므로

이 의존성만 주입하면 Hibernate를 쓸 수 있다.

근데 다른 SQL 의존성에 비해 러닝 커브가 압도적으로 높으므로, 진짜 쓸 사람이 아니면 안 쓰는 게 좋다.

시니어가 되고 싶다면 배워야 하지만.

https://dev-coco.tistory.com/76

https://spring.io/projects/spring-data-jpa

https://data-make.tistory.com/621

https://suhwan.dev/2019/02/24/jpa-vs-hibernate-vs-spring-data-jpa/

https://velog.io/@junho918/Spring-Data-Jpa-JPA..%EA%B7%B8%EB%9E%98-%EC%95%8C%EA%B2%A0%EC%96%B4..-%EA%B7%B8%EB%9E%98%EC%84%9C-%EC%8A%A4%ED%94%84%EB%A7%81-%EB%8D%B0%EC%9D%B4%ED%84%B0-JPA%EB%8A%94-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%93%B0%EB%8A%94%EB%8D%B0

https://kim-oriental.tistory.com/20

https://djunnni.gitbook.io/springboot/2019-09-05

https://devfunny.tistory.com/422




## Spring Data JDBC

위의 Spring Data JPA(와 하위 의존성인 Hibernate)는 사용이 대단히 복잡하다.

복잡성을 개선하고, 기존 Spring JDBC를 스프링 느낌으로 더 쉽게 쓸 수 있게 하기 위해 나온 모듈이다.

그러나, 현재로썬 Data JPA보다는 대중성이 떨어지고 쓰기 안 좋은 모듈 같다.

아직 성숙되지 않았다는 평도 있다. 그러니 쓸 때 신중해야 한다.

https://luvstudy.tistory.com/174

https://spring.io/projects/spring-data-jdbc

https://luvstudy.tistory.com/82

https://luvstudy.tistory.com/174

https://velog.io/@bread_dd/Spring-Data-JDBC-vs-Spring-Data-JPA

https://blog.neonkid.xyz/275

https://happy-coding-day.tistory.com/entry/%EC%A7%81%EC%A0%91-%EC%BD%94%EB%94%A9%EC%9C%BC%EB%A1%9C-%EB%8A%90%EA%BB%B4%EB%B3%B8-Spring-Data-JPA%EC%99%80-Spring-Data-JDBC-%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90




## Spring Data R2DBC

"동시성 처리"를 할 수 있는 하드웨어 리소스 매니저.

원래 DBMS는 한 명이 작업하고 있으면 그게 끝날 때까지 다른 사람이 접근할 수 없도록 blocking 개념으로 운용된다.

그러나 R2DBC를 사용하면 여러 명이 동시에 접속 및 작업을 할 수 있게 되어 성능 및 latency 개선에 도움이 많이 된다고 한다.

최근에 가장 핫한 의존성 중 하나라고 하는데, 이 의존성은 동시성 처리 개념이 들어가는 관계로

Spring 5 Webflux 구현법 숙지는 필수이다.

https://brunch.co.kr/@purpledev/28

https://webcache.googleusercontent.com/search?q=cache:a1ZLa3i6j9sJ:https://gompangs.tistory.com/entry/Spring-R2DBC-MySQL&cd=4&hl=ko&ct=clnk&gl=kr




## MyBatis Framework

### 중요도: ★★★

### Jobkorea 검색건수: 297건

DB Access Manager이다.

소스코드와 쿼리를 분리 관리할 수 있는 쿼리 매니저 같은 것인데,

XML 형태로 되어 가독성이 높고 유연성도 뛰어나다.

Apache 재단에 있던 프로그래머들이 iBatis를 만들었는데,

구글에 포섭되어 Google code에서 일하게 되었고 그 과정에서 이를 MyBatis로 업그레이드하였다고 한다.

MyBatis를 Spring에서 사용하려면, MyBatis, MyBatis-Spring, Spring-JDBC, Commons-DBCP, MySQL-Connector-java

이렇게 다섯 가지를 쓰는 것이 좋다고 한다.

JPA보다 더 자주 쓰이고, 더 자주 접하고, 더 쉽다.

https://devbin.kr/mybatis-framework-mybatis-%ED%94%84%EB%A0%88%EC%9E%84%EC%9B%8C%ED%81%AC%EB%9E%80/




## Liquibase Migration

## Flyway Migration

자료는 그대로 놓고 DBMS만 바꾸고 싶을 때 마이그레이션 툴을 쓴다고 한다.

이러한 툴에는 Flyway, Liquibase 등이 있고, 둘 중 하나를 쓸 줄 알면 되는 듯.

https://velog.io/@devsh/Liquibase-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4-%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0-Spring-Jpa-Hibernate-Liquibase-Plugin-AWS-private-database

https://ecsimsw.tistory.com/entry/Flyway%EB%A1%9C-DB-Migration




## JOOQ Access 

### Jobkorea 검색건수: 4건

MyBatis, JPA같은 DB Access 툴이다.

나는 범용성 면에서 MyBatis를 공부하는 편이 더 좋을 것 같다.

https://multifrontgarden.tistory.com/247




## IBM DB2 Driver

### Jobkorea 검색건수: 141건

IBM에서 개발한 DB2라는 DBMS를 쓸 수 있게 하나 보다.

1983년에 개발된 것으로 IBM에 종속적이고 호환성이 부족하다.

하지만 DBMS 중 가장 정교한 편에 속한다고 한다.

메인프레임 용도로 주로 사용된다고 하며, 대단히 많이 쓰이는 DBMS 중 하나이다.

쓰는 사람이 꽤 있나 보다.

https://www.ibm.com/docs/ko/tap/3.5.2?topic=SSHEB3_3.5.2/com.ibm.tap.doc/ins_install/t_ist_validate_deployment_on_weblogic_and_db2.html

http://wiki.hash.kr/index.php/%EB%94%94%EB%B9%84%ED%88%AC




## Apache Derby Database

javaDB라고 하는 것 같다.

무료 DB인데 요즘엔 좋은 게 너무 많아서 아마 쓸 일이 없을 듯..

https://i5on9i.blogspot.com/2014/08/apache-derby-1.html

https://blog.naver.com/anjdieheocp/20193372192




## H2 Database

### 중요도: ★★

### Jobkorea 검색건수: 25건

자바 기반의 오픈소스 DBMS라고 한다.

용량도 2MB여서 비용이 저렴하다. 설치과정 자체가 필요 없어서 사용이 간편하다.

디스크 기반으로 할 수도 있고 메모리 기반으로 할 수도 있다.

"브라우저 기반"의 콘솔 모드를 쓸 수도 있고, JDBC API까지 지원한다.

표준 SQL의 대부분의 문법을 지원한다.

딱 봐도 무진장 가벼워 보인다. 엄청 좋아 보인다! 그래서 테스트 단계 때 애용한다고 한다.

서버(Server) 모드와 임베디드(Embedded) 모드 두 개를 지원한다고 하며 임베디드로 많이 쓰는 것 같다.

테스트용으로 많이 쓰이니 알아두는 것이 좋다.

https://jamie95.tistory.com/188

https://dololak.tistory.com/285

https://phantom.tistory.com/59

https://oingdaddy.tistory.com/264




## HyperSQL Database

순수 자바만으로 만들었다는 DBMS.

BSD계열 라이센스를 쓰고 있어 프리웨어이고 상용 소프트웨어에서도 사용 가능하다.

그러나 H2가 이것의 후속작이라 성능이 더 좋으니, 지금 와서 이것을 쓸 일은 없다.

https://lahuman.jabsiri.co.kr/89




## MariaDB 

### 중요도: ★★★

### Jobkorea 검색건수: 488건

JDBC와 연결하여 MariaDB를 쓸 수 있다.

이 DBMS의 효용성에 대해서는 두말 할 필요가 없다.

MySQL의 후속작으로, 무료이고 성능 좋고 대중성까지 확보했다.

특히나, DBMS 시장에서 사용률이 가장 가파르게 올라가는 핫한 DBMS라 할 수 있다.

MySQL, MairaDB 둘 다 써봤는데, 고수준으로 써보지 않아 성능까진 알 수 없었지만,

사용법을 알아놓음으로써 취업에 유리해진 것은 사실이다.

중급 이상으로 올라가기 위해서 반드시 익혀놔야 할 기술스택 중 하나이다.

https://namu.wiki/w/MariaDB

https://januarysecurity.tistory.com/41




## MS SQL Server

### 중요도: ★★

### Jobkorea 검색건수: 441건

마소에서 만든 DBMS이다.

MariaDB 등 좋은 DBMS가 많아 입지가 줄어들고 있지만,

윈도 환경이 많은 게임회사에서 많이 쓴다고.

https://m.blog.naver.com/chsmanager/140210135913




## MySQL Driver

### 중요도: ★★

### Jobkorea 검색건수: 2946건

https://velog.io/@cmong/MongoDB-vs-MySQL-vs-SQLite3-%EB%AD%98%EC%93%B0%EC%A7%80




## Oracle 

### 중요도: ★★★

### Jobkorea 검색건수: 2976건
DBMS 시장을 지배하고 있는 현존 최고의 DBMS.

와우에도 오라클이 사용되었다.

누구나 인정하는 부분으로 세계 최강의 압도적인 기술력과 안정성을 자랑한다.

상용이고 비용 같은 걸로 문제가 생기는 게 단점.

https://namu.wiki/w/%EC%98%A4%EB%9D%BC%ED%81%B4%20%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4




## PostgreSQL Driver

### 중요도: ★★★

### Jobkorea 검색건수: 408건

MariaDB와 더불어 최고의 DBMS 중 하나. 

유전학습기술 뭐시기를 적용했는데,

단순 CRUD에서는 성능이 나쁜 편이지만, 복잡한 쿼리일수록 성능이 향상된다고 한다.

타입스크립트처럼 엄격한 타입체크를 적용되어 있다고 한다.

https://namu.wiki/w/PostgreSQL




## 번외편: Snowflake

### 중요도: ★

### Jobkorea 검색건수: 8건

DBMS 중 사용률이 가장 가파르게, 미친 듯이 올라가고 있는 녀석.

결제해서 쓰는 클라우드형 SaaS 소프트웨어로,

AWS처럼 클라우드 공간에 자료를 저장하여 서비스를 운용한다.

테크를 기피하던 워렌버핏도 투자를 하였다.

https://blog.lgcns.com/2510

https://signal.sedaily.com/Common/FileDownload?fileName=[%EC%8A%A4%ED%8E%98%EC%85%9C%EB%A6%AC%ED%8F%AC%ED%8A%B8_2021-7]_%EC%8A%A4%EB%85%B8%EC%9A%B0%ED%94%8C%EB%A0%88%EC%9D%B4%ED%81%AC(Snowflake)_%EB%A5%BC_%ED%86%B5%ED%95%B4_%EB%B3%B8_%EC%B5%9C%EA%B7%BC%EC%9D%98_%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C_%EA%B8%B0%EC%97%85_%EB%B3%80%ED%99%94(%EB%8B%A8%EB%A9%B4).pdf&fullPath=/Service/Branch/Signal/Report/2021/08/23/[%EC%8A%A4%ED%8E%98%EC%85%9C%EB%A6%AC%ED%8F%AC%ED%8A%B8_2021-7]_%EC%8A%A4%EB%85%B8%EC%9A%B0%ED%94%8C%EB%A0%88%EC%9D%B4%ED%81%AC(Snowflake)_%EB%A5%BC_%ED%86%B5%ED%95%B4_%EB%B3%B8_%EC%B5%9C%EA%B7%BC%EC%9D%98_%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C_%EA%B8%B0%EC%97%85_%EB%B3%80%ED%99%94(%EB%8B%A8%EB%A9%B4).pdf




## 번외편: Firebase

### 중요도: ★★

### Jobkorea 검색건수: 196건

모바일 애플리케이션을 타겟으로 한 구글 소유의 DBMS이다.

Snowflake와 마찬가지로 클라우드형 SaaS 소프트웨어였고,

모바일 계통한테 상당히 인기 있는 DBMS 같지만.. 

어째 최근 미친 듯이 성장하는 Snowflake랑 비교가 좀 된다. 

https://blog.wishket.com/%ED%8C%8C%EC%9D%B4%EC%96%B4%EB%B2%A0%EC%9D%B4%EC%8A%A4firebase%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80-%ED%8C%8C%EC%9D%B4%EC%96%B4%EB%B2%A0%EC%9D%B4%EC%8A%A4-%EC%8B%AC%EC%B8%B5-%ED%83%90/

https://namu.wiki/w/Firebase?from=firebase

https://brunch.co.kr/@second-space/5
