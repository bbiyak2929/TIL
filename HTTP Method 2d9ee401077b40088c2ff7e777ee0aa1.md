# HTTP Method

### HTTP 메소드란

클라이언트와 서버 사이에 이루어지는 요청(request) 과 응답(response)데이터를 전송하는 방식이다.

### HTTP 메소드 종류

- 주요 메소드
    - GET : 리소스 조회
    - POST : 요청 데이터 처리, 주로 등록에 사용
    - PUT : 리소스를 대체(덮어쓰기), 해당 리소스가 없으면 생성
    - PATCH : 리소스 부분 변경(PUT이 전체 변경, PATCH 일부 변경)
    - DELETE : 리소스 삭제
- 기타 메소드
    - HEAD : GET과 동일하지만 메세지 부분(body 부분)을 제외하고 , 상태 줄과 헤더만 반환
    - OPTION : 대상 리소스에 대한 통신 가능 옵션(메서드)을 설명(주로 CORS에서 사용)
    - CONNECT : 대상 자원으로 식별되는 서버에 대한 터널을 설정
    - TRACE **:** 대상 리소스에 대한 경로를 따라 메시지 루프백 테스트를 수행

### HTTP 상태코드

http 상태코드란 클라이언트가 보낸 요청의 처리 상태를 알려주는 기능

100번 ~ 500번 대를 사용

- 1XX (informational) : 요청이 수신되어 처리중
- 2XX (Succesful): 요청 정상 처리
    - 200 OK :요청 성공
    - 201 Created : 요청 성공해서 새로운 리소스 생성됨
    - 202 Accepted : 요청이 접수되었으나 처리가 완료되지 않았음
    - 204 No Content : 서버가 요청을 성공적으로 수행했지만, 응답 페이드로 본문에 보낼 데이터가 없읍
- 3XX (Rediretion): 요청을 완료하려면 추가 행동이 필요
    - 301 Moved Permanently : 리다이렉트시 요청 메서드가 GET으로 변하고, 본문이 제거될 수 있음
    - 302 Found : 리다이렉트시 요청 메서드가 GET으로 변하고, 본문이 제거될 수 있음
    - 303 See Other : 리다이렉트시 요청 메서드가 GET으로 변경
    - 304 Not Modified : 캐시를 목적으로 사용
    - 307 Temporary Redirect : 리다이렉트시 요청 메서드와 본문 유지(요청 메서드를 변경하면 안된다.)
    - 308 Permanent Redirect : 리다이렉트시 요청 메서드와 본문 유지(처음 POST를 보내면 리다이렉트도 POST 유지)
- 4XX (Client Error): 클라이언트 오류, 잘못된 문법등으로 서버가 요청을 수행할 수 없음
    - 400 Bad Request : 클라이언트가 잘못된 요청을 해서 서버가 요청을 처리할 수 없음
    - 401 Unauthorized : 클라이언트가 해당 리소스에 대한 인증이 필요함
    - 403 Forbidden : 서버가 요청을 이해했지만 승인을 거부함
    - 404 Not Found : 요청 리소스를 찾을 수 없음
- 5XX (Server Error): 서버오류 , 서버가 정상 요청을 처리하지 못함
    - 500 Internal Server Error : 서버 문제로 오류 발생, 애매하면 500 오류
    - 503 Service Unavailable : 서비스 이용 불가