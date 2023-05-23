## HashSet
HashSet이란 Set 인터페이스에서 지원하는 구현 클래스로 중복된 값을 허용하지 않으며 입력한 순서가 보장되지 않는다.

### 특징
1. 중복된 값을 허용하지 않음
2. 입력한 순서가 보장되지 않음
3. null값을 허용함

### 중복을 걸러내는 과정?
HashSet은 객체를 저장하기 전에 먼저 객체의 hashCode()메소드를 호출하여 코드를 얻어낸 후 저장되어있는 객체들의 해시코드와 비교한 뒤 equals()메소드로 두 객체를 비교하여 true가 나오면 동일한 객체로 판단하고 저장하지 않는다.<br>
<br>

### 변수선언
>HashSet<데이터타입> 변수명 = new HashSet<데이터타입>();
~~~java
HashSet<String> stringType = new HashSet<String>();
HashSet<Integer> integerType = new HashSet<Integer>();
~~~

### 추가 및 삭제
~~~java

HashSet<String> test = new HashSet<String>();

// 추가
test.add("a");
test.add("b");
test.add("c");

// 삭제
test.remove("a");
test.clear();
~~~