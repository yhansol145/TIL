## Optional
java에서 optional 은 java8 버전부터 지원한다.

### Optional이란?
NPE(NullPointException)
개발자라면 수없이 많이 마주했을 NPE이다. 해당 오류를 피하기 위해선 null값 체크를 통한 개발을 해야하는데 변수가 많고 로직이 길어질수록 코드가 더러워지게 된다.
```java
if(name != null && StringUtil.isNotEmpty(name)) {
    return name;
}
```

java8이후로는 Optional 클래스를 사용하여 NPE을 방지할 수 있다. null이 올 수 있는 데이터를 Wrapper클래스로 감싸 NPE가 발생하지 않도록 한다.<br>
Optional클래스는 아래와같이 value값을 저장하기 때문에 값이 null이여도 NPE이 발생하지 않는다.

```java
public final class Optional<T> {
    /**
     * Common instance for {@code empty()}.
     */
    private static final Optional<?> EMPTY = new Optional<>();

    /**
     * If non-null, the value; if null, indicates no value is present
     */
    private final T value;
}
```

### Optional의 활용
[Optional.empty] - 값이 null인 경우<br>
Optional은 Wrapper 클래스이기 때문에 값이 없을 수 있다. 이럴 경우에는 Optional.empty()로 생성할 수 있다.
```java
Optional<String> optional = Optional.empty();

public final class Optional<T> {

    private static final Optional<?> EMPTY = new Optional<>();
    private final T value;

    private Optional() {
        this.value = null;
    }

    ...
}
```
[Optional.of()] - 값이 null이 아닌경우<br>
데이터가 null값이 아니라면 Optional.of()로 생성한다. 이때 null값으로 데이터를 지정하려고 하면 NPE가 발생한다.
```java
Optional<String> optional = Optional.of("spring");
```

[Optional.ofNullable()] - 값이 null일수도있고 아닐수도있고..<br>
null일수도 있고 아닐수도 있는경우에 사용한다. orElse, orElseGet 메소드를 사용하여 값이 없는경우에도 안전하게 값을 가져올 수 있다.
```java
Optional<String> optional = Optional.ofNullable(getName());
String name = optional.orElse("null");
// 값이 없다면 "null" 값을 뽑는다.
```

<b>Optional</b>은 null 또는 값을 감싸서 NPE로부터의 위협에서 벗어나기 위해 등장한 클래스다. Optional은 값을 감싸고 풀고, null일 경우에는 대체하는 함수를 호출하는 등의 오버헤드가 있기 때문에 잘못 사용하게 되면 성능 저하에 문제가 생길 수 있다. 메소드의 반환값이 절대 null이 아니라면 사용을 피하는것이 좋을 것 같다. 즉 결과가 null이 될 수 있고 null에 의해 오류를 발생시킬 가능성이 있을때 사용하는 것이 좋다.