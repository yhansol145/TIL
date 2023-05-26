## Java Beans Pattern
자바빈즈 패턴은 setter 메소드로 객체 필드 값을 초기화 하는 방법을 말한다. 흔히들 setter 사용을 지양해야 한다고 하는데 그 이유는 무엇일까?<br>
1. 값을 변경한 의도를 파악하기 힘듬
   - setter를 나열한 것만으로는 어떤의도로 데이터를 변경하는지 파악하기 힘들다.
2. 객체의 일관성을 유지하기 어려움
   - 자바 빈 규약을 따르는 setter는 public으로 언제든지 변경할 수 있는 상태
   - 객체의 일관성을 유지하기가 힘들다.

## BuilderPattern
빌더패턴은 생성자의 안정성과 자바빈즈의 가독성을 다 가진 패턴이다.
- 빌더는 생성할 클래스 안에 정적 멤버 클래스로 만들어두는 것이 일반적
- 빌더 클래스의 생성자는 public 으로 선언
- 필수변수, 선택변수를 나누고 선택변수의 경우 초기화 시켜준다.

### 장점
1. 필요한 데이터만 설정할 수 있음
2. 유연성 확보
3. 가독성 향상
4. 변경 가능성을 최소화 할 수 있음

-> TODO 추가작성