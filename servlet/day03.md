# 프레임워크
프레임워크는 라이브러리처럼 다른 개발자가 만들어준 코드이다.
라이브러리는 내가 필요할 때 사용하는 도구 모음이라면, 프레임워크는 특정 목적을 가지고 만들어진 틀이며, 규칙이다.

# MyBatis Framework
관계형 데이터베이스를 자바에서 쉽게 다루도록 도와주는 프레임워크
JDBC의 문제점인 반복되는 코드를 줄여주며 JAVA코드와 SQL을 분리하여
유지보수와 분업에 유리하게 만들어준다.
또한 내부적으로 DBCP를 사용하여 커넥션 객체를 여러개 생성항고 관리하기 때문에 효율이 좋다.

# DBCP(DataBase Connection Pool)
커넥션객체를 이용하여 DB에 접근하는데 사용할 때마다 연결과 종료를 반복하면 비효율적이다.
DBCP는 일정량의 커넥션 객체를 미리 만들어두고 Connection Pool에 보관하여 필요할 때마다 커넨션 객체를 꺼내어 사용하고 반납하는 방식으로 관리해준다.
