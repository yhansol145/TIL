## Javascript 부모/자식 창 데이터 교환

웹페이지 제작 시 popup창을 여는 경우 부모창과 자식창 간 데이터 전달 방식

```javascript
// 부모창에서 popup창(자식창) 열기
window.open(URL, 타겟, option);

// 자식창에서 부모창 함수 호출
window.opener.부모창 함수;

// 자식창에서 부모창 ID값 가져오기
opener.document.getElementById(부모창 ID값).value();

// 자식창에서 부모창 ID에 value 설정하기
window.opener.document.getElementById(부모창 ID값).value = 변경값;

// 자식창 닫기
window.close(); 또는
self.close();
```