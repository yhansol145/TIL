## 타입스크립트 에러 무시

### @ts-ignore

- 자바스크립트에서는 문제가 없던 코드가 타입스크립트에서는 에러로 표시될 수 있다. 
예를들어 타입스크립트에서 unique symbol끼리는 서로 비교할 금지하지만 자바스크립트에서는 그렇지않다. <br>
다음과 같은 방법으로 에러를 없앨 수 있다.

~~~javascript
const sym1 = Symbol.for('sym'); // unique Symbol
const sym2 = Symbol.for('sym'); // unique Symbol

// @@ts-ignore
if (sym1 === sym2) {}
~~~

위와같이 에러가 나는 코드 윗줄에 @ts-ignore 주석을 달면 된다. 하지만 이 방법은 임시방편으로만 사용하는것이 좋다.

### @ts-expect-error

- @ts-ignore의 경우는 올바른코드이든 아니든 에러가 나면 무시하겠단 뜻이지만 @ts-expect-error는 다음코드는 반드시 에러가 나는 코드이지만 무시하겠다는 뜻이다.