# RestController
RESTful 서비스를 쉽게 만들수 있도록 스프링에서 제공하는 기술
일반 컨트롤러와 달리 HTML 페이지를 만들어 보내는것이 아니라 필요한 데이터만 응답에 담아 보낼 수 있다.
주로 일반 텍스트, JSON, XML타입의 데이터를 주고 받는다.

# REST(Representational State Transfer)
- 문서, 이미지, 데이터 등등의 자원을 이름으로 구분하여 데이터를 주고 받는 하나의 약속, 이때 주고받는 데이터 형식은 JSON, XML을 사용한다.
예를 들어 댓글에 대한 정보가 DB에서 가져와야하는 자원이라면, 자원의 이름을 comments라는 이름으로 정한다. 정해놓은 이름을 URL 경로에 표현하여 데이터를 주고 받는다.
이때 무엇을 할 것인지는 HTTP Method를 이용하여 구분한다.

- CRUD별 HTTP Method
1. Create : 삽입 (POST)
2. Read : 조회 (GET)
3. Update : 수정 (PUT, PATCH)
		PUT : 전체 수정
		PATCH : 부분 수정
4. Delete : 삭제 (DELETE)

정리하자면 REST란 자원을 중점으로 직관적으로 URL과 HTTP Method를 사용하여 웹서비스를 제공하는 것을 의미한다.
이렇게 REST라는 규칙을 지켜서 만든 웹 서비스를 RESTful한 웹 서비스라고 부른다. 















