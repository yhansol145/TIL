## Entity

- 테이블과의 매핑
- @Entity가 붙은 클래스는 JPA가 관리하는것으로 엔티티라고 불린다.

### 속성
- Name : JPA에서 사용할 엔티티 이름을 지정, 보통 기본값인 클래스 이름을 사용한다.
> @Entity(name = "Member")


### 주의사항
1. 접근제어자가 public 혹은 protected인 기본 생성자가 필수
2. final 클래스, enum, interface, inner 클래스에는 사용이 불가능
3. 저장하려는 속성은 final이면 안된다.
   - 구현체에 따라 되는것도 있으나 사용하지 않는것이 좋다.