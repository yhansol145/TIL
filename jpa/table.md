## Table

- 엔티티와 매핑할 테이블을 지정한다.
- 생략 시 매핑한 엔티티 이름을 테이블 이름으로 사용한다.


### 속성
Name : 매핑할 테이블 이름 (default : 엔티티 이름 사용)
Catalog : catalog 기능이 있는 DB에서 catalog를 매핑 (default : DB명)
Schema : schema 기능이 있는 DB에서 schema를 매핑
uniqueConstratints : DDL 생성 시 유니크 제약조건을 만듬. 스키마 자동 생성 기능을 사용해서 DDL을 만들때만 사용