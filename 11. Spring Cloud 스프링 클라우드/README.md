

# 11. Spring Cloud

최근 개발 트렌드는 클라우드 컴퓨팅이다.

첫째 다수의 분산서버들이 연결되어 하나의 앱처럼 동작되게 하는 MSA 환경과,

둘째 Docker 등으로 개발/운영 환경을 일관되게 관리할 수 있는 클라우드 환경

현재 이 두 가지가 가장 화두가 되는 기술 스택이다.

Spring Cloud는 높은 품질의 마이크로서비스 기반 분산시스템을 구축하는 프레임워크이다.

정확히는 마이크로서비스 기반 분산시스템을 구축할 때 기본적으로 쓰는 공통 시스템을

빠르게 구축할 수 있게 해주는 프로젝트라 할 수 있다.

자바 진영의 분산형 마이크로서비스 앱은 거의 Spring Cloud를 통해 제작된다.

(= "Spring Cloud는 자바의 MSA 아키텍처이다")

따라서 이걸 모르면 MSA를 구현할 수 없다.

Spring Cloud의 모든 해당 모듈들은 12 Factor App 방법론이 적용되어 있으므로

https://12factor.net/ko/ → 이거를 먼저 읽어볼 것.

기타 링크들도 하나씩 다 읽어볼 것.

https://www.redhat.com/ko/topics/automation/what-is-orchestration

https://go-coding.tistory.com/79

https://velog.io/@gowjr207/%EC%8A%A4%ED%94%84%EB%A7%81-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C%EB%A5%BC-%EC%84%A4%EB%AA%85%ED%95%B4%EB%B3%B4%EB%8B%A4

https://12bme.tistory.com/506

https://www.samsungsds.com/kr/insights/spring_cloud.html

https://ch4njun.tistory.com/268

https://develop-yyg.tistory.com/4




# Cloud Bootstrap

"A Spring Cloud application operates by creating a "bootstrap" context, which is a parent context for the main application."

스프링 클라우드 앱은, 메인 앱을 담당하는 최상위 컨텍스트인 Bootstrap 컨텍스트를 만들어야 동작한다.

이를 지원하기 위한 라이브러리인 듯.

CSS 부트스트랩 프레임워크랑 관련이 없다!!! 조심!!!!!!!!!

https://cloud.spring.io/spring-cloud-static/spring-cloud.html

https://develop-yyg.tistory.com/4




# Function

대충 파워업키트랑 비슷한 말인 것 같다..

https://spring.io/projects/spring-cloud-function

https://jsonobject.tistory.com/617

https://gist.github.com/ihoneymon/53811040e24f3bbfc53c371d3cd08f59

https://kyucumber.github.io/posts/spring/spring-cloud-function-kafka/




# Task

스프링 클라우드 앱에서 단기 마이크로서비스(?)를 로컬 혹은 클라우드에서 돌릴 수 있게 하는 것 같다.

Batch Processing 등을 지원하는 것 같다.

https://spring.io/projects/spring-cloud-task

https://godekdls.github.io/Spring%20Cloud%20Data%20Flow/batch-developer-guides.batch-development.simple-task/

https://memo-the-day.tistory.com/58
