## SSL
- SSL(Secure Socket Layer) 프로토콜
- SSL은 클라이언트와 서버가 암호화된 데이터를 송수신 하는 방식이다.

#### HTTP + SSL = HTTPS
- https는 http를 안전하게 만드는 방식이며 SSL프로토콜 위에서 돌아가는 프로토콜을 의미한다.

1. HTTP
- 클라이언트와 서버 사이에서 정보를 주고 받기 위해 이루어지는 요청/응답 프로토콜
- 암호화되지 않은 방법으로 데이터를 전송한다.(데이터 변조의 가능성 있음)

2. HTTPS(Hypertext Transfer Protocol Over Secure Socket Layer)
- 보안이 강화된 http
- 모든 http 요청과 응답 데이터는 네트워크로 보내지기 전 암호화된다.
- https는 http의 하부에 SSL과 같은 보안계층을 제공함으로써 동작한다.

## SSL 프로토콜 암호화
- SSL 프로토콜의 핵심은 암호화
- SSL은 보안과 성능상 이유로 대칭키와 공개키 두가지 암호화 기법을 혼용해서 사용

## SSL 인증서
- SSL 프로토콜에는 SSL 인증서가 사용된다.
- SSL 인증서는 클라이언트와 서버간의 통신을 제3자가 보증해주는 전자화된 문서