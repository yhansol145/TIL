## Day.js
자바스크립트 라이브러리<br>

자바스크립트에서 날짜/시간을 표현할때 Date 객체를 사용하거나 라이브러리를 사용하여 표현이 가능하다.<br>
Date 객체를 사용하면 YYYY년 MM월 DD일 과 같은 형식으로 날짜를 표현하기 위해선 직접 함수를 만들어 사용해야하기 때문에 라이브러리를 이용한다.<br>

- Moment.js 라이브러리는 무겁다. Moment.js의 API형식은 유지하면서 가볍게 만들어져 나온 라이브러리가 Day.js 이다.
- Day.js는 Moment.js 보다 약 33배(용량) 가벼우며 API형식이 Moment.js와 매우 유사하다.
- Day.js는 Moment.js 와 달리 변경불가능하기 때문에 이미 변수에 할당된 Day.js 객체의 날짜를 변경할 시 다시 변수에 할당해야 한다.

```javascript
var date = new Date();
date = dayjs(date).format('YYYY-MM-DD HH:mm:ss')
```

위와 같은 예제코드로 dayjs 를 통해 원하는 날짜 포맷팅값을 변경할 수 있다.