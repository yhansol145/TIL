## toLocaleString
- 인자로 전달한 Locale의 표현방식에 따라 숫자를 출력한다.
- 미국, 한국은 숫자 3자리마다 콤마(,)를 넣는다. en-US 혹은 ko-KR을 전달하면 3자리마다 콤마가 들어간다.
- 인자를 전달하지 않으면 Default Locale(3자리마다 콤마) 이 사용된다.

~~~javascript
var Quota = 256000;
var resultQuota = Quota.toLocaleString(); // default locale
    resultQuotaUS = Quota.toLocaleString('en-US'); // US locale
    resultQuotaKR = Quota.toLocaleString('ko-KR'); // KR locale
    
console.log("default : " + resultQuota);
console.log("US : " + resultQuotaUS);
console.log("KR : " + resultQuotaKR);
~~~

<br>

결과값
~~~javascript
default : 256,000
US : 256,000
KR : 256,000
~~~

<br>

### 주의사항
toLocaleString 은 Number타입 변수에만 적용이 된다. 문자열 타입 객체에 toLocaleString을 적용해도 적용되지 않는다.<br>
Number(문자열 타입 객체)로 변환 후 사용하면 된다.