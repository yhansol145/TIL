## Stream
자바8부터 추가된 컬렉션의 저장요소를 하나씩 참조하여 람다식으로 처리할 수 있도록 해주는 반복자

### 기존 루프문 처리의 문제점 ?
기존 Java에서 사용하는 for, foreach 루프문을 사용하면서 컬렉션 내의 요소들을 하나씩 다루었다.<br>
간단한 처리나 컬렉션의 크기가 작으면 별 문제는 없지만 복잡한 처리나 컬렉션의 크기가 커지면 성능저하를 일으킨다.

### Stream의 등장
컬렉션데이터를 선언형으로 쉽게 처리가 가능하다. 복잡한 루프문을 사용하지 않아도 되고 루프문을 중첩해서 사용해야 하는 경우도 이젠 없다.

#### Iterator
~~~java
ArrayList<String> list = new ArrayList<String>(Arrays.asList("a","b","c"));

Iterator<String> iterator = list.iterator();

while(iterator.hasNext()) {
    String value = iterator.next();

    if (StringUtils.equals(value, "b") {
        System.out.println("값 : " + value);
    }
}
~~~

#### for
~~~java
ArrayList<String> list = new ArrayList<String>(Arrays.asList("a", "b", "c"));

for (String value : list) {

        if (StringUtils.equals(value, "b") {
        System.out.println("값 : " + value);
    }
}
~~~

#### stream
~~~java
ArrayList<String> list = new ArrayList<String>(Arrays.asList("a", "b", "c"));
list.stream()
    .filter("b"::equlas)
    .forEach(System.out.println);
~~~


### 데이터 가공
1. filter
   - 필터는 스트림에서 나오는 데이터에서 특정 데이터만 골라낸다.
   - filter() 메소드에는 boolean값을 리턴하는 람다식을 넘겨준다.
   - 뽑아져 나오는 데이터에 대해 람다식을 적용하여 true가 리턴되는 데이터만 선별한다.

2. map
   - map()은 스트림에서 뽑아져 나오는 데이터에 변경을 가해준다.
   - map() 메소드는 값을 변환해주는 람다식을 인자로 받아,
   - 스트림에서 생성된 데이터에 map() 메소드의 인자로 받은 람다식을 적용해 새로운 데이터를 만들어낸다.

3. flatmap
   - map() 메소드와 비슷한 역할
   - flatmap() 메소드의 인자로 받는 람다는 리턴타입이 stream이다.
   - 중첩된 스트림 구조를 한단계 적은 단일 컬렉션에 대한 스트림으로 만들어준다.