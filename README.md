# Spring_Dependencies_Introduction

Concise descriptions of dependencies which is basically provided when you create a project with Spring/Springboot Initializer.

# 스프링 의존성 소개 리포를 만든 이유

스프링 프로젝트를 생성할 떄, 내가 쓸 의존성을 고르기 위해 STS에서 제공하는 Spring Initializr 혹은 https://spring.io/projects 웹사이트를 이용하게 됩니다. 여기서는 가장 많이 쓰이는(혹은 가장 많이 이름을 날렸었던) 의존성을 고를 수 있도록 그 목록을 제공하는데요. 이걸 본 저는 대체 이 의존성들 각각이 뭘 하는 놈들인지 궁금해지더라구요. 그래서 최근에 뭐가 뭔지 다 조사해서 대략적인 소개글을 만들어 보았었습니다.

하지만, 조사 결과 Initializr에서 기본 제공되는 목록이 요즘 쓰는 목록이랑 안 맞습니다. 신규프로젝트에선 아예 쓰지도 않는 라이브러리가 들어있다거나(HyperSQL Database 등) 요즘 엄청 쓰여서 당연히 있을 것 같은 게 Initalizr에선 제공되지 않는 경우도 있었습니다.(MongoDB 등). 또한 제 입장에서도 초안이 이제 완성되어 부족한 내용을 체계적으로 정리할 필요를 느꼈습니다.

이 자리에서는 Initializr에서 제공하는 의존성 목록을 베이스로 해서, 각각의 의존성들을 현재 시점에서 중요도 순으로 정리하고, 부족한 내용도 보충하기 위해 리포 형태로 관리해 가고자 합니다.
