# CRUD
	기본적인 데이터 처리 기능
	Created(생성), Read(읽기), Update(수정), Delete(삭제)

# SQL문(쿼리문)의 종류
	SQL 명령어는 명령어 성격에 따라 분류를 할 수 있다.

1. DDL(Data Definition Language) : 데이터 정의어
	- 테이블 조작 또는 제어 관련 쿼리문(테이블 생성, 수정, 삭제 등)

2. DML(Data Manipulation Language) : 데이터 조작어
	- 데이터를 조작(CRUD)하는 쿼리문

4. DCL(Data Control Language) : 데이터 제어어
5. TCL(Transaction Control Language) : 트랜젝션 제어어

----
# DML
1. SELECT : 조회
2. INSERT : 추가(삽입)

<pre><code>
INSERT INTO 테이블명(칼럼명, .....)
VALUES(값, 값,,......)
</code></pre>

3. UPDATE : 수정
<pre><code>
UPDATE 테이블명
SET 칼럼명1=값1, 칼럼명2=값2, ....
WHERE 조건식
</code></pre>
4. DELETE : 삭제
<pre><code>
DELETE FROM 테이블명
WHERE 조건식
</code></pre>

----
### TBL_MEMBER
|회원번호(pk)|이름|나이|아이디|
|----|----|----|----|
|1|철수|22|CJ|
|2|영희|25|YH|
|3|웅이|27|WO|

### TBL_BOARD
|게시물번호(PK)|제목|내용|회원번호(FK)|
|----|----|----|----|
|1|ㅎㅇ|ㅎㅇㅎㅇ|1|
|2|너무 덥다|날씨가 덥다|1|
|3|오늘은|늦잠을 잤다.|2|

# 제약조건
1. PRIMARY KEY(PK) : 기본키
- 고유한 값이며, 각 행의 구분점으로 사용된다.
- 중복이 없고 NULL값을 허용하지 않는다.
- 하나의 테이블에는 하나의 PK만 허용한다.

2. FOREIGN KEY(FK) : 외래키
- 다른 테이블의 PK를 사용하며, 중복이 가능하다.
- 보통 테이블끼리 관계를 맺을 때 사용한다.
- NULL을 허용한다.


3. UNIQUE KEY (UK) : 고유키
- NULL은 허용하지만 중복을 허용하지 않는다.



# DDL
1. CREATE : 생성
<pre><code>
CREATE TABLE 테이블명(
	칼럼명 자료형 [제약조건],
	...
);
</code></pre>
2. DROP : 삭제
<pre><code>
DROP TABLE 테이블명;
</code></pre>
3. ALTER : 수정
<pre><code>
ALTER TABLE 테이블명
- 테이블명 수정 : RENAME TO 새로운_테이블명;
- 컬럼 추가 : ADD(새로운_칼럼명 자료형);
- 칼럼명 수정 : RENAME COLUMN 기존_칼럼명 TO 새_칼럼명;
- 칼럼 삭제 : DROP COLUMN 칼럼명;
- 칼럼 타입 수정 : MODIFY(칼럼명 자료형);
</code></pre>
4. TRUNCATE : 테이블 내용 전체 삭제
<pre><code>
TRUNCATE TABLE 테이블명;
</code></pre>

## Null
- 정의되지 않은 값
- 빈 값 대신 미정 값을 부여할 때 사용
- "pk는 불가능, fk 가능, uk 가능"

## "조건식"
- NULL 은 = 으로 비교를 할 수 없으며 IS를 사용해야 한다.

## "조회시 NULL 값을 다른 값으로 변경"
- NVL(칼럼명, '값') : NULL값 대신 다른 값으로 변경하여 조회
- NVL2(칼럼명, 'NULL이 아닐때의 값', 'NULL 일 때의 값')
		NULL일 때와 아닐 때의 값을 각각 설정한다.

### NULL 값

- `NULL` 값의 정의: 데이터가 없음을 나타냄
- `NULL` 값과 관련된 연산자 및 함수
  - `IS NULL` 및 `IS NOT NULL`
  - `COALESCE` 함수
  - `NVL` 함수 (Oracle)

```sql
-- 예제: NULL 값의 처리
SELECT column1, column2
FROM table_name
WHERE column1 IS NULL;

SELECT COALESCE(column1, 'default_value') 
FROM table_name;

SELECT NVL(column1, 'default_value')
FROM table_name;


