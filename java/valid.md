## Valid

스프링부트가 제공하는 어노테이션으로 데이터 필드가 정의한 스펙에 대해 올바른 값인지를 검증한다.<br>
사이즈검증, NULL처리등의 유효성 검증이 가능하다.

### 라이브러리 추가
- maven
```java
<dependency> 
    <groupId>org.springframework.boot</groupId> 
    <artifactId>spring-boot-starter-validation</artifactId> 
</dependency>
```

- gradle
```java
dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-validation'
}
```

### @Valid Annotation
```java
@PostMapping(value="/user/{userId}/product")
public String userTest(@PathVariable long userId, @RequestBody @Valid ProductDto dto) {
	return
}
```

검증할 대상 앞에 @RequestBody 와 함께 @Valid 어노테이션을 붙여준다. 해당 인풋에 대해 유효성을 검증하겠다고 알려주는 것이다.<br><br>

```java
@Data
@Lombok
public class ProductDto{
	@NotNull(message = "상품id 값은 필수입니다.")
	private Long productId;
	
	@Size(min = 1, max = 20, message = 상품명은 1~20 글자여야 합니다.")
	private String productName;
}
```

message에는 해당 제약조건이 위배되었을 때 알릴 메세지를 지정해주면 된다.

### 제약조건 설정
- @NotNull : 해당 필드에 null값을 불허한다.
- @NotEmpty : 해당 필드에 null, ""을 불허한다.
- @NotBlank : 해당 필드에 null, "", " " 을 불허한다. 즉 최소 1글자
- @Min : 해당 필드의 최소값을 벗어나는지 검증한다.
- @Max : 해당 필드의 최대값을 벗어나는지 검증한다.
- @Pattern : 해당 필드가 특정 형태를 가지도록 검증한다. (정규표현식으로 표현함)
- @Email : 해당 필드가 이메일 형식을 가지도록 검증한다.
- @Size : 문자열의 최소, 최대 크기를 검증한다.
- @AssertTrue : 참인지
- @AssertFalse : 거짓인지
