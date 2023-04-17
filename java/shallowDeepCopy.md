## ShallowCopy & DeepCopy

배열이나 객체를 복사할 경우 복사된 데이터에 대한 이슈가 생길 수 있다.<br>
복사한 값에 의도된 값과는 다르게 값이 변해있는 경우가 있다. 이를 위해 얕은복사와 깊은복사의 차이점에 대해 정의할 필요가 있다.<br>

~~~java
public class Person {
    
    String name;
    int age;
    
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    public String getName(){
        return name;
    }
    
    public void setName(String name){
        this.name = name;
    }

    public int getAge(){
        return age;
    }

    public void setAge(int age){
        this.age = age;
    }
    
}
~~~

### Shallow Copy
얕은복사(Shallow Copy)는 주소값을 스택영역에 복사한다. 참조하고 있는 실제 값은 같다.<br>
~~~java
void shallowCopy() {
    
    Person person = new Person("유한솔", 31);
    Person copyPerson = person;
    
    copyPerson.setName("홍길동");
    copyPerson.setAge(29);
    
}
~~~
위와같이 코드를 정의하면
1. person은 유한솔, 31
2. copyPerson은 홍길동, 29의 값을 기대한다.

하지만 결과는 두 객체 모두 홍길동, 29의 값을 가지게 된다.<br>
Person copyPerson = person 코드에서 person의 참조값을 복사했기 때문이다. 즉 Heap영역에 따로 복사한 것이 아닌 person이 참조하고 있는 값을 복사한 것이다.

### Deep Copy
실제 데이터를 복사하기 위해선 깊은 복사를 해야한다. 깊은복사엔 여러 방법이 있다. 
- 복사생성자 또는 복사팩토리를 이용 
- 직접 객체를 생성하여 복사
- Clonalbe 인터페이스를 구현하여 clone() 함수를 오버라이딩

1. 복사생성자 및 복사팩토리
~~~java
//복사생성자
public Person(Person person){
    
    this.name = person.name;
    this.age = person.age
        
}

//복사팩토리
public static Person copyFactory(Person person){
    Person copyPerson = new Person(person.name, person.age);
    return copyPerson;
}
~~~

2. 직접 객체 생성
~~~java
void deepCopy(){
    Person person = new Person("유한솔", 31);
    Person copyPerson = new Person(person.getName(), person.getAge());
}

copyPerson.setName("홍길동");
copyPerson.setAge(26);

System.out.println(person); // 유한솔, 31
System.out.println(copyPerson); // 홍길동, 26
~~~
깊은 복사를 통해 복사할 경우 참조값을 복사하는것이 아니라 실제 데이터를 복사할 수 있다.

>Reference : https://jackjeong.tistory.com/100