## Connection Pool
WAS가 실행될 때 DB연결을 위해 미리 일정량의 connection 객체를 만들어 Pool에 담아두었다가 사용자의 요청이 발생하면 Pool에서 생성되어있는 connection 객체를 넘겨주고 사용이 끝나면 connection 객체를 다시 Pool에 반환하여 보관하는 기법

### 동작과정
1. 사용자가 DB를 사용하기 위해 Connection을 요청한다.
2. Pool에서 사용되지 않고 있는 Connection 객체를 제공한다.
3. 사용자가 Connection 객체를 사용완료하면 Pool로 반환한다.

어플리케이션에서 Connection Pool을 사용하면 다음과 같은 장점이  있다.
1. 서버의 부하를 줄여준다.
   - Java에서 DB Connection을 맺는 과정에서 부하가 많이 걸린다.
   - 요청이 많아지게 되면 서버에서 에러를 발생시킬 가능성이 있다.
   - Connection을 생성하고 재활용하여 서버의 부하를 줄여준다.
2. 한정된 자원의 효율적 사용
   - 서버는 한정적인 자원을 가지고 있다.
   - 요청이 올때마다 Connection을 생성한다면 성능에 문제가 생긴다.
   - Connection Pool에 미리 정해진 숫자의 Connection을 생성하여 관리한다.