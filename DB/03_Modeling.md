# 무결성 : 데이터에 결함이 없다.
- 데이터의 정확성, 일관성, 유효성이 유지되는 것

# 무결성을 판단하는 3가지 속성
1. 정확성 : 데이터가 애메하지 않아야 한다.
2. 일관성 : 각 사용자가 일관된 데이터를 볼 수 있도록 해야한다.
3. 유효성 : 데이터가 실제 존재하는 데이터야 한다.

# 무결성의 3가지 종류
1. 개체 무결성 : 모든 테이블이 pk로 선택된 칼럼을 가져야 한다.
2. 참조 무결성 : 두 테이블의 데이터가 항상 일관되 값을 가지도록 유지하는 것
3. 도메인 무결성 : 칼럼의 타입, null값의 허용 등에 대한 사항을 올바르게 정의하고 올바른 데이터가 입력되었는 지를 확인하는 것

# 모델링(기획)
1. 요구사항 분석
	- 회원, 주문, 상품 3가지를 관리하고자 한다.
	
2. 개념적 설계(개념 모델링)

	|회원|주문|상품|
	|----|----|----|
	|회원번호|주문번호|상품번호|
	|아이디	|주문날짜|상품명|
	|비밀번호|가격||
	|이름	|재고량|
	|주소	|||
	|이메일	|||		  
	|생일	|||

3. 논리적 설계(논리 모델링)

	|회원|주문|상품|
   	|----|----|----|
	|회원번호(pk)|주문번호(pk)|상품번호(pk)|
	|아이디|주문날짜|상품명|
	|비밀번호|회원번호(fk)|가격|	  
	|이름|상품번호(fk)|재고량|
	|주소|||
	|이메일(UK)|||
	|생일|||


4. 물리적 설계(물리 모델링)

	TBL_USER
	<pre><code>
	USER_ID 	VARCHAR2(1000)  PK
	PASSWORD 	VARCHAR2(1000)
	NAME 		VARCHAR2(1000)
	ADDRESS 	VARCHAR2(1000)
	EMAIL 		VARCHAR2 	UNIQUE
	BIRTH 		DATE
	</code></pre>
 
5. 구현
	<pre><code>
	CREATE TABLE TBL_USER (
		USER_ID VARCHAR2(1000),
		PASSWORD VARCHAR2(1000),
		NAME VARCHAR2(1000),
		ADDRESS VARCHAR2(1000),
		EMAIL VARCHAR2,
		BIRTH DATE,
		CONSTRAINT PK_USER PRIMARY KEY(USER_ID),
		CONSTRAINT UK_EMAIL UNIQUE(EMAIL)
	);
	</code></pre>

----

1. 요구사항
	- 핸드폰과 핸드폰 케이스를 판매한다.
	- 핸드폰을 구매하면 핸드폰 케이스도 같이 구매한다.
	- 핸드폰은 제품번호, 색상, 사이즈, 가격, 제조일, 할인율
	- 케이스는 제품번호, 색상, 가격
	- 핸드폰은 특정 케이스만 같이 구입할 수 있다.

2. 개념적 설계

	|폰|케이스|
	|----|----|
	|제품번호|제품번호|
	|색상|색상|
	|사이즈|가격|
	|가격||
	|제조일||
	|할인율||

3. 논리적 설계

	|폰|케이스|
	|----|----|
	|제품번호(PK)|제품번호(PK)|
	|색상|색상|
	|사이즈|가격|
	|가격|폰_제품번호(FK)|
	|제조일||
	|할인율||

4. 물리적 설계

	TBL_PHONE

	<pre><code>
	PHONE_ID		NUMBER			PK
	COLOR			VARCHAR2(1000)
	PHONE_SIZE		NUMBER
	PRICE			NUMBER
	SALE			NUMBER
	PRODUCTION_DATE	DATE
	</code></pre>
 
	TBL_CASE

	<pre><code>
	CASE_ID		NUMBER			PK
	COLOR			VARCHAR2(1000)
	PRICE			NUMBER
	PHONE_ID		NUMBER			FK
	</code></pre>
5. 구현
	<pre><code>
	CREATE TABLE TBL_PHONE (
		PHONE_ID NUMBER,
		COLOR VARCHAR2(1000),
		PHONE_SIZE NUMBER,
		PRICE NUMBER,
		SALE NUMBER,
		PRODUCTION_DATE	DATE,
		CONSTRAINT PK_PHONE PRIMARY KEY(PHONE_ID)
	);

	CREATE TABLE TBL_CASE (
		CASE_ID NUMBER,
		COLOR VARCHAR2(1000),
		PRICE NUMBER,
		PHONE_ID NUMBER,
		CONSTRAINT PK_CASE PRIMARY KEY(CASE_ID),
		CONSTRAINT FK_PHONE FOREIGN KEY(PHONE_ID)
				REFERENCES TBL_PHONE(PHONE_ID)
	);
 	</code></pre>

----

1.요구사항 분석

	도서관에서 회원의 정보와 책의 정보가 필요하다.
	회원의 정보는 회원번호, 이름, 나이, 핸드폰 번호, 주소가 필요하고
	책의 정보는 도서번호, 책이름, 카테고리가 필요하다.
	단, 카테고리는 인문학, 추리, IT, 로맨스만 가능하다.
	한 명의 회원은 여러권의 책을 빌릴 수 있다.
	테이블 명 TBL_MEMBER, TBL_BOOK

2. 개념 모델링
   
	|회원|책|
	|----|----|
	|회원번호|책번호|
	|회원이름|책이름|
	|나이|카테고리|
	|핸드폰 번호||
	|주소||

3. 논리 모델링

	|회원|책|
   	|----|----|
	|회원번호(PK)|책번호(PK)|
	|회원이름|책이름|
	|나이|카테고리(CHECK)|
	|핸드폰 번호|회원번호(FK)|
	|주소||

4. 물리 모델링

	TBL_MEMBER
	<pre><code>
	MEMBER_ID	NUMBER         PK
	MEMBER_NAME	VARCHAR2(1000)   
	AGE		NUMBER
	PHONE      	VARCHAR2(1000)
	ADDRESS      	VARCHAR2(1000)
	</code></pre>
 
	TBL_BOOK
	<pre><code>
	BOOK_ID      NUMBER           PK
	BOOK_NAME    VARCHAR2(1000)   
	CATEGORY     VARCHAR2(1000)   CHECK('인문학', '추리', 'IT', '로맨스')
	MEMBER_ID    NUMBER           FK
	</code></pre>
5. 구현

	<pre><code>
	CREATE TABLE TBL_MEMBER (
		MEMBER_ID NUMBER,
		MEMBER_NAME VARCHAR2(1000),   
		AGE NUMBER,
		PHONE VARCHAR2(1000),
		ADDRESS VARCHAR2(1000),
		CONSTRAINT PK_MEMBER PRIMARY KEY(MEMBER_ID)
	);
	
	CREATE TABLE TBL_BOOK (
		BOOK_ID NUMBER,
		BOOK_NAME VARCHAR2(1000),   
		CATEGORY VARCHAR2(1000),
		MEMBER_ID NUMBER,
		CONSTRAINT PK_BOOK PRIMARY KEY(BOOK_ID),
		CONSTRAINT FK_MEMBER FOREIGN KEY(MEMBER_ID)
								REFERENCES TBL_MEMBER(MEMBER_ID),
		CONSTRAINT CK_BOOK CHECK(CATEGORY IN ('인문학', '추리', 'IT', '로맨스')
	);
	</code></pre>


