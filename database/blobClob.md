## Blob & Clob

- Blob과 Clob은 데이터베이스 용어로 대용량의 이진 데이터나 문자열 데이터를 저장하는 데 사용되는 데이터 유형이다.

### Blob(Binary Large Object)
Blob은 이진 데이터를 나타내는 데이터 유형이다. 주로 이미지, 동영상, 음악 파일 등과 같은 바이너리 형식의 대용량 데이터를 저장하는데 사용한다.<br>
Blob데이터는 그 자체로는 해석되지않고 애플리케이션에서 필요에 따라 읽고 처리해야 한다.<br><br>

웹 애플리케이션에서 사용자가 프로필 사진을 업로드하면 해당 사진은 Blob으로 저장될 수 있다.<br> 
데이터베이스에서 Blob은 이진 형식으로 저장되며 필요할때마다 읽거나 업데이트 할 수 있다.

### Clob(Character Large Object)
Clob은 문자열 데이터를 나타내는 데이터 유형이다. Clob은 매우 큰 텍스트 데이터를 저장하는 데 사용된다.<br>
긴 문서, 웹 페이지 내용 또는 XML문서와 같은 대용량 문자열 데이터를 저장할 수 있다.<br><br>

Blob과 마찬가지로 Clob데이터는 그 자체로는 해석되지 않는다. 데이터베이스에서는 문자열 형식으로 저장되며 필요에따라 읽거나 수정할 수 있다.

> Blob과 Clob은 대용량 데이터를 효율적으로 저장하고 검색하는 데 사용하며 다양한 데이터베이스 시스템에서 지원된다.