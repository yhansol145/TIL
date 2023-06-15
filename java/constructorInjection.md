## 생성자 주입

> @Autowired를 사용하는 의존성주입보다 생성자주입을 더 권장하는 이유??

### 의존성 주입 방법

1. 생성자 주입(Constructor Injection)
스프링에서도 권장하는 방식으로 스프링 프레임워크 4.3버전부터는 의존성 주입으로부터 클래스를 완벽하게 분리할 수 있다.<br>
```java
@Component
public class Test {

	private final TestService testService;

}
```

2. 필드 주입(Field Injection)
필드에 @Autowired를 붙여주면 자동으로 의존성이 주입된다.
```java
@Component
public class Test {

	@Autowired
	private TestService testService;

}
```

3. 수정자 주입(Setter Injection)
setter를 이용한 주입방법으로 네이밍 패턴이 꼭 set~~일 필요는 없다.
```java
@Component
public class Test {

	private TestService testService;
	
	@Autowired
	public void setTestService(TestService testService) {
		this.testService = testService;
	}

}
```

의존성 주입방법중 2번 필드주입을 대체로 많이 사용한다. 그런데 언젠가부터 인텔리제이가 경고를 한다.
> Spring Team recommends: “Always use constructor based dependency injection in your beans. Always use assertions for mandatory dependencies”.
스프링에서 생성자 주입을 권장한다.

### 생성자 주입방법을 권장하는 이유
1. 순환참조를 방지할 수 있다.
순환참조가 발생하는 경우 애플리케이션이 구동되지 않는다. 생성자 주입방법 이외의 방법으로 의존성을 주입하게 되면 애플리케이션은 문제없이 구동되지만 메소드가 수행되면 오류가 발생한다.
2. 테스트에 용이하다.
테스트코드를 조금 더 편리하게 작성할 수 있다. 
```java
SomeObject someObject = new SomeObject();
MadComponent madComponent = new MadComponent(someObject);
madComponent.someMadPlay();
```
3. 오류를 방지할 수 있다.
생성자 주입방법을 사용하면 선언된 필드는 final이다. 따라서 런타임 시점에 변경할 수가 없다. 다른값을 참조하도록 변경하지 못하기 때문에 NPE와같은 오류를 컴파일 시점에 방지할 수 있다.