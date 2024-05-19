# 클래스
1. 사용자 정의 타입이다. (자료형)
	- 클래스를 사용하면 여러 타입, 여러 값을 저장할 수 있는 저장 공간을 만들 수 있다.

2. 객체를 생성하기 위한 틀, 설계도이다.

3. 연관성이 있는 저장공간과 기능을 한 곳에 모아 편하게 관리할 수 있는것

# 객체(Object)와 인스턴스(instance)
- 객체 : 실제 사물 또는 개념
- 클래스 : 객체를 컴퓨터에 옮기기 위해 추상화한 것
* 추상화 : 어떤 것의 특징(속성, 행위)을 추려내는 과정
- 인스턴스 : 클래스를 이용하여 메모리에 저장공간을 만든 것
	물리적으로 존재하는 공간

# 클래스 선언
class 클래스명{
	변수; // 멤버 변수, 필드

	메서드(){} // 멤버 메서드

         // class를 구성하는 모든 필드, 메서드 등을 합쳐서 멤버라고 부른다.
*추상화 : 어떤 것의 특징(속성, 행위)을 추려내는 과정
- 인스턴스 : 클래스를 이용하여 메모리에 저장공간을 만든 것
	     물리적으로 존재하는 공간

# 클래스 선언
class 클래스명 {
	변수; // 멤버 변수, 필드
	
	메서드(){} //멤버 메서드 

	// class를 구성하는 모든 필드, 메서드 등을 합쳐서 멤버라고 부른다.
}

# 인스턴스화(객체화) : instantiation
	객체를 만드는 작업
	추상적인 개념을 구체화시키는 작업

	클래스명 변수명 = new 클래스명();

# 객체 사용 방법
	변수명.멤버명
	.(점) : 하위 연산자, 멤버접근 연산자 ,....

=========================================================================
# 생성자
- 클래스 이름 뒤에 소괄호가 있는 형태
- 메서드와 비슷하지만 메서드라고 부르지 않는다.

  생성자는 리턴이라는 기능이 존재하지 않는다.
- 객체를 생성할 때 실행되는 코드가 작성되어 있다.
- 주로 해당 객체의 필드를 초기화하는 목적으로 사용한다.

# 기본생성자
- public 클래스명() {}
- 매개변수가 없다.
- 클래스 선언 시 자동으로 선언되며, 개발자가 직접 생성자를 선언하게되면 자동으로 만들어주지 않는다.

# this
- 객체 자기 자신을 의미한다. -> 객체 자신의 주소값을 담고 있다.
