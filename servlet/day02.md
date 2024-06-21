# 서블릿(servlet)
서블릿은 자바 기반의 웹 어플리케이션을 개발할 때 사용하는 기술이다.
서블릿은 서버에서 실행되며 클라이언트의 요청을 처리하고 동적인 웹 컨텐츠를 생성하는 역할을 한다.
요청방식에 따라 실행되는 메서드가 갈리게 된다.
HttpServlet 클래스를 상속받아 만든수 있다.

# HTTP 요청 예시

```
GET /submit-form HTTP/1.1
Host: www.example.com
Content-Type: application/json
Content-Length: 33
Accept-Encoding: gzip, deflate
Connection: keep-alive

{
  "name": "John",
  "age": 30
}
```
# HTTP 응답 예시

```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 27

{
  "status": "success"
}
```

요청과 응답을 주고 받을때 위와 같은 텍스트를 직접 작성한다면 매우 불편하다.
우리는 웹 브라우저의 주소창, html의 form태그와 submit버튼을 통해 편하게 요청을 보낼 수 있다.

# JSP(Java Server Page)
JAVA를 기반으로 만든 웹 프로그래밍 기술이다.
서블릿의 불편한 점을 개선하고자 HTML 코드사이에 JAVA코드를 작성할 수 있게 만들었으며, 동적인 페이지를 만드는데 특화되어 있다.
JSP도 서블릿 클래스처럼 서블릿 컨테이너가 관리하며, 서블릿 컨테이너가 JSP를 실행 시킬 때 서블릿으로 변환하여 실행한다. 즉, JSP는 내부에서 서블릿으로 변환되어 실행된다.

# GET방식과 POST 방식
클라언트가 입력한 데이터를 서버에 전송할 때 요청 방식에 따라 차이가 있다.

- GET : 데이터의 양이 적으며, 주소에 노출되어도 상관없을 때 사용(게시판 페이지 정보, 단순 페이지 이동)
	주소(URL)에 데이터를 추가하여 전달하는 방식
	쿼리 스트링을 사용한다.
	- 쿼리 스트링
	주소 뒤에 ?로 시작하는 텍스트
	주소?parameter=value&parameter="value&....
	
	주소에 데이터가 추가되므로 길이에 제한이 있으며 데이터가 노출되므로 보안상 취약하지만 상대적을 빠르다는 장점이 있다.
	
- POST : 데이터 양이 많으며, 민감한 정보를 포함하는 경우(로그인,회원가입, 글쓰기 정보)
	데이터를 주소가 아닌 요청 본문(body)에 저장하여 전송한다.
	데이터의 길이에 제한이 있지만 GET방식 보다 대용량의 데이터를 전송할 수 있다.
	보안상 GET방식 보다 상대적으로 좋지만 다른 보안 처리를 하지 않으면 여전히 취약하다.
	상대적으로 느리다.




























