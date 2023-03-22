## BeanUtils.copyProperties
- 'Apache Commons BeanUtils' 라이브러리에서 제공하는 메소드
- 두개의 Java객체 사이에서 속성 값을 복사하는데 사용된다.

1. 소스객체의 getter 메소드를 호출하여 속성값을 가져온다.
2. 대상객체의 setter 메소드를 호출하여 해당 속성값을 설정한다.
3. 소스객체와 대상객체 간의 속성 이름이 동일하다는 가정하에 이루어진다.

> BeanUtils.copyProperties 를 사용할때는 대상객체가 반드시 빈(bean)규약을 따라야 한다. 즉, 대상객체는 기본 생성자와 속성에 대한 getter/setter 메소드를 가지고 있어야 한다.

### 몇가지의 단점
1. 복사중 예외 발생 가능성
   - 소스객체와 대상객체 간 속성이름이 동일하지 않거나 대상객체가 빈 규약을 따르지 않는 경우 복사작업 중 예외가 발생할 수 있다.
2. 속성타입 변환 문제
   - 소스객체와 대상객체 간 속성타입이 다를 경우 문제발생.(예시.문자열과 숫자형일 경우)
3. 리플렉션 오버헤드
   - 리플렉션을 사용하여 복사하기 때문에 런타임에 많은 오버헤드를 초래할 수 있다. (성능저하)
4. 불안정성
   - Apache Commons BeanUtils 라이브러리는 더이상 개발되지 않고 있다. 보안취약점 및 기타 버그에 노출될 가능성이 있다.
   - Spring Framework 혹은 Apache Commons PropertyUtils 라이브러리 사용 권장
     (https://commons.apache.org/proper/commons-beanutils/apidocs/org/apache/commons/beanutils/PropertyUtils.html)