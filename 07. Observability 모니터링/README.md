
# 7. Observability

다양한 모니터링 툴들이 속해있는 곳이다.

용도 별로 뭘 써야 할지도 모르겠고, 인지도는 뭐가 높은지 잘 모르겠다.

모니터링 툴이 필요할 경우 살펴봐야 되겠다.

이렇게 앱의 상태를 모니터링하고 제어할 수 있는 툴을 "액츄에이터"라고도 하는 것 같다.

https://incheol-jung.gitbook.io/docs/study/srping-in-action-5th/chap-16.

마이크로서비스에 대한 정보는 아래 링크 참조.

https://happycloud-lee.tistory.com/category/Micro%20Service/mSVC%EA%B0%9C%EB%B0%9C




## Datalog

모니터링 서비스이다.

SaaS(Software As A Service) 즉 구독형 형태로 판매한다고 한다.

정확히 뭔지조차 모르겠다. 국내 웹에 정보가 아예 안 나온다. 아무도 안 쓰는 것 같다..




## Influx

### 중요도: ★

### Jobkorea 검색건수: 5건

TSDB(Time-Series DataBase)는 시간 순서로 저장되는 데이터 통칭 시계열 데이터를 다루는 DBMS 형식으로,

모니터링을 위한 로그 저장에 특화되어 있다.

그리고 이러한 TSDB 중에서 가장 인기가 많은 것이 Influx인데,

이걸 스프링에서 쓸 수 있게 하는 의존성이라고 한다.

Influx는 Go언어로 만들었으며, NoSQL이고, 오픈소스이다.

Influx는 단순히 DBMS이므로, 여기에 특정 기준으로 데이터를 넣어주는 입력기도 필요할 것이고

그러한 데이터를 출력해서 화면에 보여주는 출력기도 필요할 것이다.

입력기는 주로 시스템 모니터링 및 지표 수집 에이전트(실행기)인 Telegraf라는 것을 함께 물려서 사용한다.

※ Influx를 만든 회사인 InfluxDB사에서 제작했다

출력기로는 주로 Grafana라고 데이터를 이쁘게 보여주는 서비스에 주로 물려서 쓴다고 한다.

※ Grafana는 오픈소스 메트릭(데이터의 시각화) 전문 도구이다.

그렇게 구현된 모니터링 저장 및 화면출력 시스템 구조는 아래와 같다.

user ──< 조회 >─→ grafana → {influxDB} ←─< 데이터전송 >── telegraf

Jobkorea 검색 건수도 적고 사용 빈도는 높지 않지만, 자꾸 눈에 밟힌다.

대규모 서비스를 제작하려면 이런 게 있다는 사실을 알고는 있어야 되겠다.

https://www.inflearn.com/questions/342442

https://kmdigit.github.io/2020/03/20/using-influxdb-spring/

https://www.44bits.io/ko/keyword/grafana

https://musma.github.io/2019/07/08/getting-started-with-influxdb-time-series-database.html

https://si.mpli.st/dev/2017-09-10-introduction-to-telegraf/




## Graphite

Grafana와 똑같은 역할을 하는 시각화 툴이다. 주로 차트 만드는데 쓴다고 한다.

둘 중에 하나만을 배워야 한다면 Grafana를 배우는 것이 훨씬 낫다.

Grafana가 비록 Spring Starter가 제공하는 기본 의존성은 아니지만

실제론 Graphite보다 압도적으로 더 많이 쓰이기 때문이다.

(Jobkorea 검색건수: Grafana 66건 vs Graphite 10건 미만)

https://meetup.toast.com/posts/237

https://logz.io/blog/grafana-vs-graphite/

https://coralogix.com/blog/grafana-vs-graphite/




## New Relic

상용 모니터링 서비스이다. SaaS이다.

매월 100G의 데이터가 무료라고 하는데 일단 부분유료긴 한 것 같다.. 

https://newrelic.com/kr




## Prometheus

### 중요도: ★

### Jobkorea 검색건수: 50건

Grafana와 같은 모니터링 의존성인데, Grafana보다 인기가 훨씬 더 많다.

참고로 모니터링 툴을 써야 할 정도로 규모가 큰 서비스라면

모니터링 의존성을 한 개가 아니라 여러 개를 섞어 조합해서 쓰는 경우도 있다고 하는데,

이 경우 Prometheus 메인 + Grafana를 서브 < 요렇게 조합해서 쓴다고 한다.

일단 네이버가 자바 앱 모니터링에 이렇게 쓴다고 한다.

※ Graphite를 물려서 쓰는 경우는 많지 않다.

https://meetup.toast.com/posts/237




## Sleuth

대규모 마이크로서비스에서는 한 개의 동작만 실행해도

그 과정에서 수많은 마이크로서비스들이 유기적으로 연결되어 순차적으로 동작한다.

이때 중간에 문제가 생기면 어디서 문제가 생겼는지 알기가 정말 어려운데

그런 일련의 작동 트래픽들을 추적 모니터링하는데 특화된 모니터링 의존성이다.

트위터에서 제작하였으며, 오픈소스이다.

https://docs.spring.io/spring-cloud-sleuth/docs/current/reference/html/




## Wavefront

상용 모니터링 서비스이다. SaaS이다.

서버에서 발생한 이벤트가 발생되면 이걸 클라우드 공간으로 전송하는 식으로 기록하며,

이후 웹으로 확인할 수 있게 한 것이 특징이다.

https://velog.io/@lsb156/Spring-Boot-Wavefront-Sample-%EC%A0%95%EB%A6%AC




## Zipkin Client

### 중요도: ★

위의 Sleuth랑 함께 물려 쓰는 모니터링 툴 같다.

클라우드 모니터링이 가능하다고 한다.

https://happycloud-lee.tistory.com/216

https://engineering.linecorp.com/ko/blog/line-ads-msa-opentracing-zipkin/




※ 번외편: Jaeger, Zipkin, Sleuth

Jaeger > Zipkin >>>> Sleuth 순으로 인기가 많다.

Jobkorea 검색건수: Jaeger 10건 > Zipkin 3건 > Sleuth 0건

이 셋은 이론상 함께 쓸 수 있다.(Jaeger랑 Zipkin은 한 쪽으로 호환이 된다고 함)

그치만 셋이나 필요한 상황이 있을까 싶다.

또한, 해외에서 그러는데 Kubernetics를 쓰면 Jaeger가 좋다고 하지만

우선 Jaeger를 써보고 안 맞으면 Zipkin을 대신 쓰는 식을 권장한다.

https://logz.io/blog/zipkin-vs-jaeger/
