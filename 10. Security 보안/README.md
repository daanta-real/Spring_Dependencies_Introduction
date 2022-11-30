

# 10. Security

스프링에서 말 그대로 보안 관련된 처리를 담당한다.

인증과 인가의 개념 차이 https://dextto.tistory.com/234

SSO(Single-sign-on) https://toma0912.tistory.com/75




## Spring Security

인증, 권한에 대한 처리를 Filter를 이용해서 할 수 있는 스프링 하위 프레임워크다.

Intercepter는 Dispatcher를 지난 뒤 Controller로 가는 과정에서 실행되지만,

필터는 Dispatcher로 가기 전에 적용되므로, 이쪽이 좀더 강력하다고 할 수 있다.

이 Spring Security는 기반 프레임워크이다. 다양한 프레임워크를 붙여 쓸 수 있다.

그러나 현재는 이걸 직접 쓰지 않고 다른 툴을 덧붙여서 쓰는 듯?

https://mangkyu.tistory.com/76

https://velog.io/@seongwon97/Spring-Security-Spring-Security%EB%9E%80

https://lotuus.tistory.com/78

https://velog.io/@shawnhansh/Spring-Security%EC%99%80-OAuth2-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0




## OAuth2 Client

### 중요도: ★

### Jobkorea 검색건수: 42건

권한이 있는 사용자의 접근만 허용하게 하는 권한인증 서버를 만드는 데 쓰이는 인증시스템 라이브러리다.

"스프링 시큐리티는 리액티브 어플리케이션을 위한 OAuth2와 웹플럭스 통합을 지원한다."

라고 하는데 아직 무슨 말인지 모르겠다..

OAuth2는 약간 기본 베이스 같은 거고 위에 다양한 라이브러리를 붙여 쓸 수 있나 보다. 

Kakao OAuth2도 있다고 한다. 한번 써보고 싶은데!

https://heijang.github.io/springsecurity/spring-security-oauth2-client/

https://brunch.co.kr/@sbcoba/4

https://www.skyer9.pe.kr/wordpress/?p=2367

https://iseunghan.tistory.com/300

https://galid1.tistory.com/582




## OAuth2 Resource Server

OAuth2 Resource Server를 돌리기 위한 거라고 하는데..

OAuth 2.0 Bearer 토큰이란 걸로 API를 보호하고 싶을 때? 쓴다고 한다.

https://www.skyer9.pe.kr/wordpress/?p=2405

https://velog.io/@cjy9306/Spring-boot%EC%9D%98-Resource-Server-%EA%B5%AC%ED%98%84

https://godekdls.github.io/Spring%20Security/oauth2webflux/

https://godekdls.github.io/Spring%20Security/projectmodules/




## Spring LDAP

### Jobkorea 검색건수: 15건

사용자 인증 정보를 중앙 집중적이면서도 분산형 디렉토리 서버 즉 계층형 형태로 저장하는

간단한 인증 프레임워크라고 한다. 읽기 속도를 높이는데 주안점을 두었다고.

임베디드 자바에서 돌릴 수 있는 가벼운 프레임워크인 게 장점이지만, 구조가 복잡하다는 단점도 있다.

https://memo-the-day.tistory.com/157

https://shanepark.tistory.com/303

https://www.blocko.io/developer/ldap-%EC%9D%B8%EC%A6%9D/




## Okta

### Jobkorea 검색건수: 16건

Spring Boot에서 OAuth2를 쓰려면,

예전에는 Spring-security-oauth2 라이브러리를 사용해서 인증 서버를 제작하였다고 하나,

그 프로젝트는 Deprecated되었기 때문에 현재는 쓰지 않는다고 한다. 

현재는 Keycloak이나 Okta를 쓴다고 하고, 느낌상 Keycloak이 Okta보다 더 좋은 것 같다. 

국내에서 아직 사용자 저변이 많이 넓진 않은 것 같고, 게다가 오픈소스가 아니어 보여 더더욱 좀 그렇다.

https://kudl.tistory.com/entry/Okta%EC%98%A5%ED%83%80-SSOOIDC-Open-ID-Connect-Application-%EB%A1%9C%EA%B7%B8%EC%9D%B8

https://ttubeoki.tistory.com/31

https://blog.naver.com/getinthere/221746448099

https://ko.quish.tv/spring-security-tutorial

https://hammerstudy.tistory.com/11

https://www.inflearn.com/questions/226012




## 번외편: Keycloak

계정 관리와 Access 관리를 해준다고 한다.

국제적인 인증, 인가 표준을 모조리 제공한다.

SSO(Single-sign-on)이 가능하며, 오픈소스라고 한다.

Spring Security 측에서 인증서버의 지원을 "중지"했다고 했으므로, 저거 대신에 이걸 쓰는 게 좋겠다.

쏘카에서 현재 쓰고 있다. 믿을 수 있는 것 같다!!

https://alice-secreta.tistory.com/28

https://www.inflearn.com/questions/226012

https://league-cat.tistory.com/397

https://www.swit.or.kr/download.do?fileName=/202012/[keycloak]%20Solution%20Guide%20V0.4_20181203.pdf

https://memo-the-day.tistory.com/105

https://tech.socarcorp.kr/security/2019/07/31/keycloak-sso.html
