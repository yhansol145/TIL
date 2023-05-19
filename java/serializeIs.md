## Serialize

자바에서 시리얼라이즈는 객체를 일련의 바이트로 변환하여 저장하거나 전송하는 과정을 말한다.<br>
'java.io.Serializable' 인터페이스 구현 필요<br><br>

일반적으로 시리얼라이즈 작업을 수행할 때 객체의 필드 값을 저장하는데, 필드에 대한 getter메서드를 호출하여 값을 얻는다.<br><br>

자바 VO 혹은 자바 Bean에 boolean 타입의 is~ 로 시작하는 메소드를 선언했을 때 시리얼라이징 과정에서 해당 메소드가 의도치 않게 실행될 수 있다. is~ 함수가 의도치 않게 실행되어 NPE와 같은 오류가 발생할 가능성이 있다.
<br><br><br>
> JavaBeans specification

시리얼라이징 과정에서 is~ 함수가 실행되는 이유는 자바 빈 규칙에 따른 것이다.<br>
예를들어 isMatch() 메소드가 is로 시작하여 boolean값을 반환한다면 시리얼라이즈 작업에서 해당 필드 값을 저장하기 위해 해당 메소드가 호출될 수 있다.

~~~java
public class MyClass implements Serializable {
    
    private boolean valid;
    
    public boolean isValid() {
        return valid;
    }
    
}
~~~
- 위의 코드에서 isValid() 메소드는 is로 시작하지만 실제로는 get 메소드로 동작한다.
- 시리얼라이징을 수행하면 isValid() 메소드의 반환값인 valid필드의 값이 저장된다.
