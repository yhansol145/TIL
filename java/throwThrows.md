## throw와 throws의 차이점

- throw : 에러를 고의로 발생시킬 때 사용
- throws : 자신을 호출한 상위 메소드로 에러를 던지는 역할


### throw
```java
public class Person {
    
    public Person(String name) {
        if(name == null) {
            throw new NullPointerException();
        }
    }
    
}
```
Person 클래스의 생성자를 보면 위와같이 name 값이 null 일 때 throw를 통해 강제로 에러를 발생시킨다.<br>
위와같이 throw를 통해 에러를 강제로 만들었을 때 try/catch 로 해결하지 않으면 throws를 이용해 호출한곳으로 에러를 던지게 한다.

### throws
```java
public class OutPutStream {
    
    public OutPutStream(String name) throws FileNotFoundException {
        this(name != null ? new File(name) : null, false);
    }
    
}
```
OutPutStream 클래스의 생성자를 보면 throws FileNotFoundException을 볼 수 있다.<br>
메소드 생성자 선언부에 예외를 선언함으로써 이 메소드를 사용하기 위해서 어떠한 예외들이 처리되어져야 하는지 쉽게 알 수 있다.<br>
자바에서는 메소드를 작성할 때 메소드 내에서 발생할 가능성이 있는 예외를 선언부에 명시하여 사용하여 이 메소드를 사용하는 쪽에서는 이에 대한 처리를 하도록 강요한다.


> 에러를 던지지 않고 내부적으로 해결하고 싶다면 try/catch를 사용하여 해결하고, 반대로 try/catch로 에러처리를 하지 않는다면 선언부에서 throws를 통해 에러를 던져야 한다.
<br>

1. 예외를 메소드의 throws를 명시하는 것은 예외를 처리하는 것이 아님
2. 자신을 호출한 메소드에게 예외를 전달하여 예외처리를 떠맡기는 것
3. main메소드에서도 예외처리가 되지 않으면 main메소드가 종료되어 프로그램 종료
