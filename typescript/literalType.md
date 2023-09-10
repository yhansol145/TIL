## Literal Types

- TypeScript의 리터럴 타입은 string, number 두 가지가 있다. 이를 사용하면 문자열이나 숫자에 정확한 값을 지정할 수 있다.

### 문자형 리터럴 타입
~~~javascript
type Food = "rice" || "noodle" || "meat"

const myFood1: Food = "rice";
const myFood2: Food = "abc"; // Error: Type 'aaa' is not assignable to type 'Food'.
~~~

위 코드에서 Food에서 허용한 3개의 문자열 외에 다른 문자열을 사용하게 되면 에러가 발생한다.

~~~javascript
type Grade = 1 || 2 || 3

const student1: Grade = 1;
const student2: Grade = 5;
~~~


숫자형도 마찬가지로 허용한 숫자 이외의 값을 할당한 경우 에러가 발생한다.
