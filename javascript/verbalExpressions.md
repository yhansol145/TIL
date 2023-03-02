## verbalExpressions
정규식을 쉽게 사용할 수 있는 라이브러리<br>

>https://github.com/VerbalExpressions

~~~javascript
VerEx()
    .startOfLine()
    .then()
    .maybe()
    .endOfLine()
~~~

1. 핸드폰번호 정규식
- 010-1234-1234
```javascript
<script>
    var 정규식 = VerEx()
                .startOfLine()
                .range('0', '9') // 0에서 9까지 숫자
                .repeatPrivious(3) // 3자리
                .maybe('-')
                .range('0', '9') // 0에서 9까지 숫자
                .repeatPrivious(4) // 4자리
                .maybe('-')
                .range('0', '9') // 0에서 9까지 숫자
                .repeatPrivious(4) // 4자리
                .endOfLine()
    console.log(정규식.test('010-1234-1234'));
</script>
```

<br>

2. URL 도메인 정규식
- www.naver.com
```javascript
<script>
    var 정규식 = VerEx()
                .startOfLine()
                .then('http')
                .maybe('s')
                .then('://')
                .anything()
                .endOfLine()
    console.log(정규식.test('https://www.naver.com'));
</script>
```