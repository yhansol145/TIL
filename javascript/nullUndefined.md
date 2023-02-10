## undefined
- 아무것도 할당받지 않은 상태를 뜻한다.
- var 키워드로 선언한 변수는 undefined 로 초기화
- 변수를 선언한 후 값을 할당하지 않으면 undefined

```javascript
var name;
console.log(name); //undefined
```

## null
- 비어있는, 혹은 존재하지 않는 값
- 변수가 이전에 참조하던 값을 더이상 참조하지 않을때 null

```javascript
var name = document.getElementById('id')
console.log(name); //'id'를 가진 요소가 없다면 null
```