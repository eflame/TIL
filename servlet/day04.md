# forward
요청과 응답을 특정 파일에 전달하여 처리한다.
보통 jsp파일로 전달하여 HTML코드를 완성시켜 해당 HTML을 응답에 담아 클라이언트에게 보내줄 때 사용한다.

req.getRequestDispatcher("파일경로")forwoard(req,resp);

# redirect
resp.sendRedirect("URL경로");
클라이언트의 브라우저를 특정 URL로 재요청하도록 한다.
