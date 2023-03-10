## Serverless
- 개발자가 직접 서버를 관리하는 것이 아닌 호스팅 플랫폼에서 서버를 관리
- 호스팅 플랫폼에 배포하면 플랫폼에서 알아서 관리하고 운영을 해준다.

### 사용이유
직접 서버를 관리하는데 어려운점이 많다.
1. 앱사용/트래픽 -> 하드웨어 스펙문제, 소프트웨어 관리 문제, 서버 모니터링 등
2. 항상 운영해야 한다는 이유로 비용적인 측면도 고려해야 한다.

### 방법
- 코드를 구성하는 함수를 만든다.
- 클라우드 호스팅 플랫폼에 등록한다.
- 언제 해당 함수를 실행하는지 플랫폼에 명시해준다.

### 장점
1. 개발자가 서버 구축과 관련하여 관리할 필요가 없다.
2. 확장이 쉽다.(스케일링)
3. 사용한만큼만 비용이 측정되기 때문에 비용적인 측면에서 이득이 있다.

### 단점
1. 처음시작하는데 시간이 걸린다.(Cold Start)
2. 리소스의 한계가 있다.(메모리사이즈 등)
3. 함수 timeOut(오래걸리는 함수, 무거운 함수는 적합하지 않다.)
4. 독립적, 개별적인 함수로 만들어야 한다.