---
title:  "마이크로서비스 핵심 원칙들"
excerpt: "마이크로서비스 어플리케이션은 자율적인 서비스의 집합이다."

categories:
  - MSA
tags: 
  - MSA
last_modified_at: 2021-02-12T12:05:22+09:00
---

마이크로서비스 어플리케이션은 **자율적인 서비스**의 집합이다. 


## 핵심 원칙 5가지 
### 자율성(Autonomy)
다른 서비스와 독립적으로 변경되고 운영된다
- 느슨한 결합
- 독립적으로 배포 가능

자율성은 문화에 관한 것이기도 하다.
비즈니스 영향력의 전달을 담당하는 팀에게 서비스의 소유권과 책임을 위임!

### 회복성(Resilience)
마이크로서비스는 장애를 격리하는 자연스러운 매커니즘이다.
마이크로서비스를 독립적으로 배포하면 애플리케이션 또는 인프라스트럭처의 장애는 시스템의 일부애만 영향을 미친다.
새로운 기능을 빅뱅 방식으로 출시하는 것 보다 작은 기능으로 배포하는 것이 시스템을 점진적으로 변화시키는데 도움을 준다.
장애가 발생할 때 확산을 막으려변 발생한 일을 처리해야한다. 가능한 부분에 비동기 처리를 하고 적절한 회로 차단기와 타임아웃을 사용하도록 설계해야한다.
시스템 모니터링도~

### 투명성(Transparency)
시스템이 어느 지점에서나 투명하고 관찰 가능해야 문제를 관찰하고 진단할 수 있다.
애플리케이션의 모든 서비스는 비지니스, 운영, 인프라스트럭처 메트릭과 애플리케이션 로그, 요청 추적을 생성하며... 결국 엄청난 양의 데이터를 이해해야 한다.

### 자동화(Automation)
마이크로서비스는 단일 어플리케이션을 개발하는 것 보다 훨씬 더 복잡한 아키텍처를 가진다.
자동화를 도입하고 서비스간 일관된 인프라스트럭처를 만들면 부가적인 복잡성을 관리하기 위한 비용을 줄일 수 있다.

데브옵스(devops), 인프라스트럭처 코드화(infrastructure-as-code) 

### 동기화(Alignment)
각 팀간의 커뮤니케이션 방법이나 프로세스등 최소한 표준과 기술적인 수준을 맞추는 과정
어느 일정 수준 이상으로 팀의 능력을 끌어 올려주고, 전체 팀에서 사용하는 최소한의 공통 프로세스등에 대해서는 서로 맞춤


## 소프트웨어 개발의 목적
https://www.infoq.com/news/2015/04/north-kerr-complexity-code/

> The goal of software development is to sustainably minimise lead time to business impact.
>
> 소프트웨어 개발의 목적은 궁극적인 비즈니스 영향력(business Impact)을 전달하는 데 소요되는 시간을 최소화하는 것이다.
>
> _댄 노스(Dan North)_

> Kerr and North both stated that the goal of a software development is to minimise lead time to business impact, and to do this in a sustainable fashion.
> [Lead time] is a technical term, taken from the lean methodology, and is essentially the wall-clock time from a business requirement being formulated, to a solution being implemented which impacts the business in a positive fashion (which may, or may not, require the development of software).

[Lead time] : https://en.wikipedia.org/wiki/Lead_time

복잡한 소프트웨어 시스템에서 어려운 부분은 변경 요건이 있을 때 지속 가능한 방식으로 비즈니스 가치를 전달하는 것이다.
그리고 시스템의 규모가 커지고 복잡해지더라도 계속해서 기민하게 반복적이고 안전하게 요구사항을 반영하는 것이다.
그러므로 잘 설계된 복잡한 시스템이란 마찰과 위험의 2가지 요소가 시스템 전반에 걸쳐 최소화되는 것일 것이다.

## 기타 여러가지

### 컨웨이의 법칙([Conway’s Law])
> Any organization that designs a system (defined broadly) will produce a design whose structure is a copy of the organization's communication structure.
>
> _Melvin E. Conway_
> 
> 소프트웨어의 구조는 그 소프트웨어를 만드는 조직의 구조와 일치한다
> 
[Conway’s Law] : https://en.wikipedia.org/wiki/Conway%27s_law

### 마이크로서비스는 마찰과 위험을 줄여준다.
마이크로서비스는 다음 3가지 발식으로 마찰과 리스크를 줄여준다.
- 개발할때 의존성을 격리시키고 최소화 함
- 개발자가 전체 시스템 보다는 응집된 개별 구성요소에 대해 추론할 수 있음
- 작은 독립적은 변경을 지속적으로 전달할 수 있음

### 어려운 점
- 마이크로서비스의 범위를 정하고 식별하는데는 대상에 도메인에 대한 상단한 지식이 필요하다.
- 서비스간의 올바른 경계와 계약을 식별하는 것이 어렵고, 한번 정한 후 변경하는 데 많은 시간이 소요된다.
- 마이크로서비스는 분산 시스템이므로 시스템의 상태, 일관성, 네트워크 신뢰성에 대해 다른 가정을 전제해야한다.
- 시스템 구성요소를 여러 네트워크에 분산하고 혼재된 기술의 수가 늘어나면 마이크로서비스에는 새로운 형태의 장애가 생긴다.
- 정상 상태에서는 무엇이 발생해야하는지 이해하고 검증하는 것이 더욱더 어렵다.
- 테스트가 더 어려워진다. 서비스들이 각각 분리가 되어 있고, 다른 서비스에 대한 종속성을 가지고 있기 때문에, 특정 기능을 테스트하고자 할 경우 여러 서비스에 걸쳐서 테스트를 진행해야 하기 때문에 테스트 환경 구축이나 문제 발생시 분리된 여러개의 시스템을 동시에 봐야 하기 때문에 테스팅의 복잡도가 올라간다.
- 트랜젝션 처리의 어려움


## 마이크로서비스 트랜젝션 처리
### Try-Confirm/Cancel 
- REST 기반의 간단한 분산 트랜잭션 : https://www.popit.kr/rest-%EA%B8%B0%EB%B0%98%EC%9D%98-%EA%B0%84%EB%8B%A8%ED%95%9C-%EB%B6%84%EC%82%B0-%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-%EA%B5%AC%ED%98%84-1%ED%8E%B8/
- Try-Confirm/Cancel: https://dzone.com/articles/transactions-for-the-rest-of-us

### Two-Phase Commit, SAGA pattern
- https://medium.com/giljae/%EB%A7%88%EC%9D%B4%ED%81%AC%EB%A1%9C-%EC%84%9C%EB%B9%84%EC%8A%A4%EC%97%90%EC%84%9C-%EB%B6%84%EC%82%B0-%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-347af5136c87
- https://microservices.io/patterns/data/saga.html
- https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/

### MSA에서 메시징 트랜잭션 처리하기
https://www.popit.kr/msa%EC%97%90%EC%84%9C-%EB%A9%94%EC%8B%9C%EC%A7%95-%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-%EC%B2%98%EB%A6%AC%ED%95%98%EA%B8%B0
