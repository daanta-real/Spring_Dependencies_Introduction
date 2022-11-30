
# 12. Spring Cloud Circuit Breaker

"서킷 브레이커"

주식시장의 그것과 같다.

여러 마이크로서비스를 돌릴 때 문제가 있는 서비스가 발견하면 알아서 끄게 함으로써

전체 앱의 서비스에 지장이 생길 만한 상황을 방지해 준다.

이것을 "Fault Tolerance(장애감내, 실패감내)"라 부른다고 한다.

서킷브레이커에는 Netflix Hystrix, Resilience4J, Alibaba Sential, Spring Retry 등

다양한 제품이 있는데, Hystrix는 개발진이 EOS(End Of Service)

즉 더이상 개발되지 않는다고 선언함으로써 Deprecated되었으며,

현재는 이 대체품으로 Resilience4j의 사용을 권장한다고 한다.

그 외에도 다른 라이브러리도 각각 대체품이 있으나,

블로그 글이 거의 Resilience4j 뿐이라서 걍 이걸로 대동단결 되어가는 느낌.




# # Resilience4j

https://happycloud-lee.tistory.com/219

https://cheese10yun.github.io/resilience4j-basic/

https://luvstudy.tistory.com/150

https://sabarada.tistory.com/205

https://bottom-to-top.tistory.com/57

https://wedul.site/654
