

# 13. Spring Cloud Config

스프링 클라우드앱 제작 중 설정이 변경되었을 때, 내가 처음부터 빌드 > 배포해야 하는데

이를 앱이 자동으로 할 수 있게 도와주는 의존성들이다.

Spring Boot Starter인가? devtools인가?하는 녀석의 분산서비스 버전이다.

https://happycloud-lee.tistory.com/209

https://madplay.github.io/post/introduction-to-spring-cloud-config

https://mangkyu.tistory.com/253

https://velog.io/@18k7102dy/Spring-Cloud-cloud-config%EC%97%90-%EB%8C%80%ED%95%9C-%EC%84%A4%EB%AA%85-%EB%B0%8F-%EA%B5%AC%ED%98%84

https://happycloud-lee.tistory.com/209

https://ch4njun.tistory.com/268

https://devbksheen.tistory.com/entry/Spring-Cloud-Config-%EC%86%8C%EA%B0%9C-%EC%98%88%EC%A0%9C

https://otrodevym.tistory.com/entry/spring-boot-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0-14-spring-cloud-config-%EC%84%A4%EC%A0%95-%EB%B0%8F-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%86%8C%EC%8A%A4

https://wonit.tistory.com/502

https://yaboong.github.io/spring-cloud/2018/11/25/spring-cloud-config/




## Config Client

스프링 분산시스템 셋팅을 클라이언트에서 조작할 수 있게 해주는 녀석 같다.

Spring Boot 2.4 이후로 클라이언트쪽 셋팅 방법이 변경되었다고 한다.

https://ingnoh.tistory.com/109

https://godekdls.github.io/Spring%20Cloud%20Config/spring-cloud-config-client/

https://multifrontgarden.tistory.com/278

https://velog.io/@tkaqhcjstk/%EC%8A%A4%ED%94%84%EB%A7%81-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-spring-cloud-config-2

https://devguide.tistory.com/entry/%EC%A0%9C4%EC%9E%A5-Spring-Cloud-Config-Config-Client-%EA%B8%B0%EB%B3%B8



## Config Server

각 마이크로앱의 설정을 중앙 서버 한 군데에서 통제할 수 있게 해준다.

위의 것들과 연동해서 쓰는 것인가 보다.

https://cheese10yun.github.io/spring-config-server/

https://yongkyu-jang.medium.com/spring-cloud-config-server-f1e390f18cfc

https://blog.leekyoungil.com/?p=352



## Vault Configuration

스프링부트 클라우드 분산앱을 설정할 때 Vault를 이용할 수 있게 해주는 의존성인 듯.

https://www.vaultproject.io/

https://www.vaultproject.io/docs/configuration



## Apache Zookeeper Configuration

### Jobkorea 검색건수: 11건

스프링부트 클라우드 분산앱을 설정할 때 Apache Zookeeper를 이용할 수 있게 해주는 의존성인 듯.

https://appleg1226.tistory.com/13



## Consul Configuration

### Jobkorea 검색건수: 3건?

위랑 비슷한 거지만

"클라우드 환경에서 서비스를 연결(Connect), 보안(Secure) 및 구성(Cofigure)하는 분산 Service Mesh"

이라고 한다. WEB에서 UI를 지원한다고.

https://techblog.woowahan.com/2586/
