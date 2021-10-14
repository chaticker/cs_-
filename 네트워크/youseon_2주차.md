# HTTP의 GET방식과 POST방식의 차이점

클라이언트에서 서버로 요청할 때 사용하는 HTTP 메소드 방식

### GET

- 요청하는 데이터가 url에 key와 value가 결합된 쿼리 스트링 형태로 HTTP Request Message의 Header에 담겨 전송된다.
- 전송할 수 있는 데이터의 크기가 제한적이다.
- url에 전송하는 데이터가 노출되어 보안에 취약하다.
    
    ```
    	(예시 https://recordboy.github.io/login?id=user&pw=1234)
    ```
    

### POST

- 요청하는 데이터가 HTTP Request Message의 Body 부분에 담겨 전송된다.
- 대용량 데이터를 전송할 수 있다.
- 전송하는 데이터가 노출되지 않아 GET방식에 비해 보안성이 높다. (하지만 암호화 필요)