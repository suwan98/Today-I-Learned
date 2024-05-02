# CORS (교차 출처 리소스 공유)

## CORS

- 출처를 구성하는 세 요소(프로토콜,도메인,포트)중에서 하나라도 다르다면 `CORS Error`가 발생한다.

![alt text](/cs/aseets/cors.png)

- 따라서 CORS를 설정한다는 의미는 출처가 다른 서버간의 리소스 공유를 허용한다는 의미

<br />

## 동일 출처 정책이 필요한 이유는?

- 만일 제약이 없다면, 해커가 CSRF(Cross-Site Request Forgery)나 XSS(Cross-Site Scripting) 등의 방법을 이용해서 우리가 만든 어플리케이션에서 해커가 심어놓은 코드가 실행하여 개인 정보를 가로챌 수 있다.
- 출처(Origin)의 동일함은 두 URL의 구성 요소 중 Protocol(Scheme), Host, Port 이 3가지만 동일하다면 동일 출처로 판단한다.

<br />

## 브라우저의 CORS 기본 동작

### 1. 클라이언트에서 HTTP 요청 헤더에 Orgin을 담아 전달한다.

- 기본적으로 웹은 HTTP 프로토콜을 통해 서버에 요청을 보내는데, 이때 브라우저는 요청 헤더에 Origin이라는 필드에 출처를 함께 담아 보내게 된다.

### 2. 서버는 응답헤더에 Access-Control-Allow-Origin을 담아 클라이언트에 전달한다.

- 이후 서버가 요청에 대한 응답 헤더에 `Access-Control-Allow-Origin`이라는 필드를 추가하고 값으로 이 리소스를 접근하는것이 허용된 출처 url을 내려보낸다.

### 3. 클라이언트에서 Origin과 서버가 보내준 Access-Control-Allow-Origin을 비교한다.

- 이후 응답을 받은 브라우저는 자신이 보냈던 요청의 Origin과 서버가 보내준 응답의 Access-Control-Allow-Origin을 비교해본 후 차단할지 말지를 결정한다.
- 만약 유효하지 않다면 그 응답을 사용하지 않고 버린다. (CORS 에러 !!)
- 위의 경우에는 둘다 http://localhost:3000이기 때문에 유효하니 다른 출처의 리소스를 문제없이 가져오게 된다.

**결국 CORS 해결책은 서버의 허용이 필요**

- 서버에서 `Access-Control-Allow-Origin`헤더에 허용할 출처를 기재해 클라이언트에 응답하면된다.
- 즉 백엔드 개발자가 고쳐야 될 부분!
