## fetch
Node.js의 API중 하나인 fetch API에 대해 알아보자.<br>
- fetch API는 URL을 통해 네트워크 요청을 해주는 api<br>
- fetch API를 통해 네트워크에 접근이 가능하고 http요청, 파일다운로드 등의 작업이 가능하다.

~~~javascript
const fetchResponsePromise = fetch(resource [, init]);
~~~

#### Parameters

- resource : URL or Request object
- options : request에 추가로 넣고싶은 Object
  - method: 사용할 메소드(get, post, put, delete)
  - headers : 헤더에 전달할 값
  - body : 바디에 전달할 값(JSON.stringIf(data))
  - cache : 캐쉬 사용여부
- Return value : Promise객체를 반환
- 네트워크 문제로 요청이 실패하면 promise는 reject 된다.

~~~javascript
const newUrl = "www.naver.com"

fetch(newURL)
    .then(console.log);
~~~