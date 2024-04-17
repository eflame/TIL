- Collections 클래스
	컬렉션 프레임워크에 관련된 여러 메서드를 지원하는 클래스
	대부분 static 메서드로 구현되어있으므로 따로 객체생성은 필요하지 않다.

- collections 클래스 메서드
1. sort() : 리스트 객체를 넘겨주면 리스트의 요소를 오름차순으로 정렬한다.
   sort(리스트객체, collections.reverseOrder()) : 내림차순으로 정렬한다.

2. reverse() : 리스트 객체를 넘겨주면 요소를 뒤집어준다.

3. shuffle() : 리스트 객체를 넘겨주면 요소를 랜덤으로 정렬시킨다.

4. max() : 리스트의 요소중 최대값을 반환한다.

5. min() : 리스트의 요소중 최소값을 반환한다.

- set : 집합
	1. 데이터의 순서를 보장하지 않는다.
	2. 순서가 없기 때문에 중복값을 허용하지 않는다.
	3. 순서가 없기 때문에 값을 가져오는것이 불가능하다.
	4. 데이터 탐색을 목적으로 사용한다.

- set 인터페이스를 구현하는 구현 클래스

- HashSet
1. set 인터페이스를 구현한 가장 대표적인 클래스다.
2. 중복되는 값을 저장하면 무시한다.
3. 인덱스가 존재하지 않아 순서를 보장하지 않으며 ArrayList나 배열처럼 값을 가져오는것이 불가능하다.
4. 객체의 hashCode() 메서드가 반환하는 해시코드를 이용하여 데이터를 처리하기 때문에
   데이터를 읽어오는데 속도가 상대적으로 빠르다.
5. 위 특징 때문에 데이터의 존재 여부를 파악할때 사용하기 좋다.

** 주의할점 : HashSet에 들어갈 객체의 equals()메서드를 오버라이딩 했다면
	   반드시 HashSet이 중복값을 판별할 수 있도록 hashCode()메서드도 오버라이딩 해야한다.

** HashSet은 데이터를 가져올수 없으므로 Iterator같은 자료구조를 변환하여 값을 가져와야한다.

- Iterator
	컬렉션에 저장된 데이터들을 컬렉션의 종류와 관계없이 동일한 방식으로 데이터를 가져오기 위한
	인터페이스이다.
	어떠한 자료구조든 Iterator로 변환하면 Iterator만의 방식으로 순서를 만들고 값을 가져올 수 있다.

- Iterator 과련 메서드
	1. iterator()
		ArrayList, HashSet등의 컬렉션의 객체를 Iterator타입으로 변환해주는 메서드

	2. hasNext()
		다음 요소의 존재유무를 파악하여 boolean타입으로 반환한다.

	3. next() 
		다음 요소값을 가져온다. 다음요소를 가져올려고 할때 아무 값도 없다면
		예외가 발생한다.

- Map 
	데이터의 순서를 보장하지 않는다.
	데이터를 Key와 Value한 쌍으로 저장하여 Key로 해당 Value에 접근할 수 있다.
	Key는 배열의 인덱스처럼 값에 접근하기위한 용도로 사용한다.
	Key값은 중복을 허용하지 않지만
	Value값은 중복을 허용한다.
	
- Map인터페이스를 구현한 구현 클래스

- HashMap
	hashCode()가 반환하는 해시코드를 이용하여 데이터 검색속도가 상대적으로 빠르다.
	이미 저장된 Key를 가진 한쌍의 데이터(요소)를 넣으면 가장 마지막에 넣은 Value로 수정된다.
	저장되지 않은 Key를 가진 한쌍의 데이터를 넣으면 새롭게 추가된다.

- JSON(Javscript Object Notation) : 자바스크립트 객체 표기법
	데이터를 표현하는 방법이다.(단순 텍스트)
	데이터를 저장,전송할 때 많이 사용되는 표기법이다.
	기존에 데이터를 전송할때는 XML,CSV를 많이 사용했지만 이제는 이해하기 쉽고 용량도 적은
	JSON형식을 많이 사용한다.
	어떤 언어를 사용하더라도 JSON형식으로 데이터를 전송할 수 있다.

- JSON의 형식(Map과 유사하다)
	{"key1" : value1 , "key2" : value2};