## Arrow Function
ES6(ECMAScript6) 부터 지원하는 js 함수 생성방식이다. =>(화살표) 표시를 사용하여 함수를 선언할 수 있다.<br>
param =>[함수코드] 와 같은 방식으로 구현하게 되는데 이 함수는 파라미터의 경우에 따라 여러방식의 함수를 선언할 수 있다.<br><br>

화살표함수는 function 키워드보다 간단하게 함수를 선언할 수 있다.

### ES5 / ES6
```javascript
// ES5
var es5 = function(a,b) {
    return a+b;
}
var sum = es5(1,2);
console.log(sum);

// ES6
var es6 = (a,b) => {
    return a+b;
}
var result = es6(1,2);
console.log(result);
```

위 코드는 ES5에서 사용하던 function과 arrowFunction을 비교한 코드이다. 두 함수는 동일하다.
- 화살표 함수를 호출하기위해 예제의 ES6와 같은 할당변수를 작성한다.
- function 키워드 사용 안함
- 소괄호 안에는 파라미터 작성