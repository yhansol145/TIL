## Session Clustering
세션클러스트링이란 WAS가 2대 이상 설치된 환경에서 세션을 공유하는 것이다.
세션을 공유하여 대체된 WAS에서도 동일한 세션을 관리하는것을 의미한다.<br><br>
WAS에서 접속자 수가 초과할 경우 다른 WAS를 사용하게 되는데 이때 발생할 수 있는 세션 불일치 문제를 해결할 수 있다.

### 클러스터링?
- 여러대의 서버를 한가지 업무를 수행하도록 만든것이다.
- 여러대의 서버를 운용하면 하나의 DB에서 에러가 발생해도 다른 DB에서 역할을 수행할 수 있어 지속적인 서비스 제공이 가능하다.
    1. 노드 장애시에도 다른 서버로 클라이언트에게 서비스 제공
  2. 프로그램 병렬화 및 관리의 어려움이 있다.

### 세션 클러스터링 종류
1. WAS 구성
 - 데이터별 Primary/BackUP 인스턴스를 지정하여 구성, 별도의 서버 인프라가 필요없다.
2. 세션 서버 구성
 - 별도의 세션 서버가 필요하며 세션 공유 설정이 용이하다. 성능은 글쎄?
3. 세션 데이터그리드 구성
 - JVM 프로세스 수 에서 세션정보를 저장하며 확장성과 안정성을 보장한다. 별도의 서버 구성이 필요하며 관리포인트가 증가한다.(Tomcat)

참고자료 : https://junshock5.tistory.com/91