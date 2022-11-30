

# 18. Template Engines

템플릿 엔진은 지정된 양식을 지켜 텍스트를 작성하면 동적으로 HTML을 생성해 주는 프레임워크이다.

1) 가장 기본적인 건 JSP, JSTL 등인데 얘네는 거의 레거시 취급으로 사양된지 오래이다.

JSP는 서버측 데이터 즉 비즈니스 로직을 페이지 렌더링하면서 다루다 보니까

컨트롤러와 모델이 서로 뒤섞이고 프론트엔드와 백엔드의 업무 구분이 애매모호해지고

제약사항도 많고, 준비할 것도 많으며(각종 import 등) 설정도 추가해야 하니 불편하다.

해서 더이상 권장할 수 없게 되었다.

2) 요즘에는 스프링부트에서 공식적으로 지원하는 템플릿 엔진인

Thymeleaf, Freemaker, Mustache, Groovy 등을 쓴다.

3) 하지만, 이것도 결국 없어도 되는 엔진이 추가되는 점은 동일하므로 있는 것 자체로 성능이 떨어진다.

그래서, 템플릿 엔진으로 백 > 프론트로 데이터 넘길 것 없이

프론트에서 React+API 등으로 데이터를 따로 받아 렌더링하기도 한다.

4) Tailwind는 Bootstrap같은 CSS쪽 프레임워크이다. Thymeleaf와 혼동하지 말 것.

https://istoryful.tistory.com/269

https://jangcool.tistory.com/entry/Java-Template-%EC%84%B1%EB%8A%A5-%EB%B9%84%EA%B5%90

https://www.inflearn.com/questions/72824

5) 놀랍게도 템플릿 엔진의 성능은 Thymeleaf가 가장 나쁘다고 한다. JSP보다도 나쁘다고..

정확한 성능은 Mustache > Freemarker > Velocity > JSP > Thymeleaf



https://offbyone.tistory.com/410




## Thymeleaf

스프링부트에서 공식적으로 지원하는 템플릿 엔진이다.

vue.js처럼 태그에 속성을 매기는 방식으로 작동하는데, 이중에 인기가 가장 많다.

문법이 어려워 진입장벽이 높은데, 거의 vue.js 배우는 급 같다.

좋은 엔진이지만, 이거 할 시간이면 React를 공부할 수 있다.

어쩔 수 없이 화면을 찍어야 할 때만 쓸 것.

https://blog.naver.com/bgpoilkj/221982228705

https://imgzon.tistory.com/97

https://myeongdev.tistory.com/20




Apache Freemarker

아파치에서 개발한 템플릿 엔진이다.

자유도가 매우 높은 대신, 너무 많은 기능을 제공하여

상황에 따라 비즈니스 로직을 추가해야 할 경우도 있어서 곤란할 때가 있다.

역시 React 공부하는 게 낫다고 생각.

※ 프리메이커(free maker)가 아니라 프리마커(free maRker) 이다!!!! 

https://yuniel.tistory.com/37




Mustache

이것도 많이 쓴다.

자유도를 극단적으로 낮춰 기능을 한정시킨 대신 진입장벽이 대단히 낮은 것이 특징.

써보면서 정말 쉬워서, 이래서 템플릿 엔진을 쓰는구나 확 느낌이 왔다.

(${변수명} 이런 식으로 값만 불러올 수 있다. ← 사용법 이게 다임..)

프론트/백의 업무분리가 확실히 되며, 무려 양쪽에서 쓸 수도 있는 게

자바에서 쓰면 템플릿 엔진이 되고, 자바스크립트에서 쓰면 클라이언트 엔진이 된다!

다른 장점도 진짜 많다, IntelliJ를 커뮤니티 버전으로 쓰는 사람은

Thymeleaf, Freemaker 등을 지원하지 않지만 Mustache는 100% 지원하고

자바/자바스크립트 말고도 엄청나게 많은 언어를 지원하기 때문에 나중에 스택 갈아타기도 쉽다.

템플릿 엔진을 꼭 하나만 익혀야 한다면 추천하는 것은 이것.

React를 쓰기 애매한 규모의 사이트에 적용할 만한 진정한 템플릿 엔진은 이거라고 본다.

기능이 너무너무 없어 결정적인 순간에 입맛을 다시는 경우가 있는 게 흠.

https://melonicedlatte.com/2021/07/25/202100.html

https://kkambi.tistory.com/43




Groovy Templates

유명하다고는 하는데 위의 3개 보다는 잘 안 쓰는 것 같다.

개인적으로는 공부하지 않을 생각이다.