## Optional Chaining

자바에선 null값 체크를 위해 Optional<T> 문법을 사용한다.
자바스크립트에도 null값 체크를 위해 사용할 수 있는 문법인 Optional Chaining 기능이 있다.

~~~javascript
<script>
    var user = {
        name: 'hansol',
        age: 30
    }
    
    console.log(user.name)
    
</script>
~~~

user 오브젝트 안에 있는 name값을 출력하기 위해서는 console.log(user.name) 과 같이 코드를 작성한다.
근데 user 객체가 빈 값이라면??
~~~javascript
console.log(user?.name)
~~~

'?.' 과 같이 작성하면 왼쪽이 비어있으면 오른쪽값을 리턴하지 않는 문법이다.
이를 Optional Chaining 문법이라고 한다.

- ?. : optional Chaining 연산자
- ?. 왼쪽이 null, undefined이면 해당자리에 undefined을 내려준다.
- 해당문법은 에러를 해결해주는 것이 아닌 감추는 것이기 때문에 필요한곳에만 쓰도록 하자.


## Nullish Coalescing

데이터가 null값이면 대신해서 보여줄 데이터

~~~javascript
<script>
    var user;
    
    console.log(user ?? '호호호;')
</script>
~~~

- '??' 왼쪽 데이터가 없으면 오른쪽을 출력한다. 
- user 객체가 빈값 혹은 undefined 라면 '호호호;' 문자열을 대신 출력해준다.