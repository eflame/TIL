# DCL : DB에 접근하는 권한을 제어하는 명령어
	GRANT : 계정에 권한을 부여하는 명령어 <br>
		GRANT 권한 [ON 테이블명] TO 계정;
  
	REVOKE : 계정에 권한을 제거(회수) 하는 명령어<br>
		 REVOKE 권한 [ON 테이블명] FROM 계정;

계정 만들기
1. SYS 계정으로 접속하여 계정을 생성한다.

		CREATE USER 계정이름 IDENTIFIED BY 비밀번호;

접속 권한 주기

	  GRANT CREATE SESSION TO 계정명;

테이블 접근 권한 부여하기

	GRANT [SELECT, UPDATE, DELETE, INSERT] ON 테이블명 TO 계정명;

계정 삭제하기

	DROP USER 계정명;
	
접속과 여러 권한을 한 번에 처리하기(관리자 급 권한 부여)

	GRANT CONNECT, RESOURCE, DBA TO 계정명;



























