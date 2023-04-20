## 마이크로서비스
마이크로서비스는 소프트웨어가 잘 정의된 API를 통해 통신하는 소규모의 독립적인 서비스로 구성되어 있는 경우의 스포트웨어 개발을 위한 아키텍처 및 조직접 접근방식이다.<br>
마이크로서비스 아키텍처는 애플리케이션의 확장을 용이하게 하고 개발 속도를 앞당겨 새로운 기능의 출시 시간을 단축할 수 있게 해준다.

![microService](../image/microService.png)

> MONOLITH

모놀리식 아키텍처의 경우 모든 프로세스가 긴밀하게 결합되고 단일서비스로 실행된다. 애플리케이션의 프로세스에 대한 수요가 급증하면 해당 아키텍처 전체를 확장해야 한다. 코드베이스가 증가하게 되면 기능을 추가하거나 개선하기가 복잡해진다. 모놀리식 아키텍처는 애플리케이션 가용성에 대한 위험을 가중시킨다.

> MICROSERVICES

마이크로서비스 아키텍처의 경우 애플리케이션이 독립적인 구성요소로 구축되어 각 프로세스가 서비스로 실행된다. 각 서비스마다 한가지 기능을 수행한다. 서비스가 독립적으로 실행되기 때문에 특정 기능에 대한 수요를 충족하도록 각각의 서비스를 업데이트, 배포 및 확장할 수 있다.

### 특징
1. 자율성
    - 각 구성 요소 서비스는 다른 서비스의 기능에 영향을 주지 않는다.
    - 서비스가 해당 코드 또는 구현을 다른 서비스와 공유할 필요가 없다.
    - 개별구성요소 간 통신은 정의된 API를 통해 이루어진다.
2. 전문성
   - 각 서비스는 일련의 기능을 위해 설계되며 특정 문제를 해결하는데 중점을 둔다.
   - 서비스가 복잡해지면 더 작은 서비스로 분할할 수 있다.

### 장점
- 독립적이면서 신속하게 업무를 수행할 수 있어서 개발 주기 시간이 단축된다.
- 해당 서비스를 독립적으로 확장할 수 있다.
- 인프라의 규모를 조절하고 기능의 비용을 측정할 수 있고 수요가 증가하여도 가용성을 유지할 수 있다.
- 테스트가 용이하고 문제가 발생할 경우 간단하게 롤백이 가능하다.
- 각 작업별로 적합한 도구를 선택할 수 있다.(작업별로 언어, 툴 등을 다르게 사용 가능)
- 소프트웨어를 소규모 모듈로 분할하면 코드를 재사용할 수 있다.
- 서비스가 독립적으로 동작하기 때문에 모놀리식 아키텍처보다 복원성이 좋다.

참고자료 : https://aws.amazon.com/ko/microservices/