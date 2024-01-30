## 전개연산자(Spread Operator)

전개연산자는 배열의 요소나 객체를 나열해주는 연산자<br>
배열이나 객체의 복사본을 만들 수 있으며 여러개의 배열이나 객체를 손쉽게 병합할 수 있다.<br><br>

### 배열

```typscript
const hansol = {
    name: 'Hansol Yoo',
    occupation: 'Backend Developer',
    age: 30,
    website: 'github.com/yhansol145'
};
```

위의 예제에서 name과 website만 다르고 나머지는 비슷한 오브젝트를 만든다고 가정할 때 전개연산자를 사용할 수 있다.

```typescript
const gildong = {
  ...hansol,
  name: 'Gildong Hong',
  website: 'github.com/gildong',
};
```

위 코드는 hansol 오브젝트에서 name, website를 오버라이드 한 것

### 객체

```typescript
const arr = [1, 2, 3];

let test_arr = [4, 5, 6];
let test_arr2 = [4, 5, 6];

test_arr.push(arr);
console.log(test_arr);
// [4,5,6, [1,2,3]]

test_arr2.push(...arr);
console.log(test_arr2);
// [4,5,6,1,2,3]
```

push할때 전개연산자를 사용하지 않은 코드는 array전체가 들어가 2차원 배열이 되지만
전개연산자를 사용하면 array 내부의 요소 하나하나가 삽입된다.
