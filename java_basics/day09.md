## 객체지향 프로그래밍(Object Oriented Programming)
   추상화된 클래스로 객체를 만들고 객체들간의 관계를 맺어 상호작용하는 프로그래밍 기법

## 객체지향 언어의 특징
   1. 상속
   2. 다형성
   3. 추상화
   4. 캡슐화

## 클래스(Class)
   1. 클래스는 객체를 생성하기위한 틀,설계도이다.
   객체는 기능과 속성으로 이루어져 있는데 속성은 변수와같은 저장공간으로
   기능은 메서드로 표현한다. 그 변수,메서드를 선언하는곳이 클래스이다.

   2. 클래스는 사용자정의 타입이다(클래스도 자료형이다.)
   클래스를 사용하면 여러타입,여러값을 저장할수 있는 저장공간을 만들 수 있다.
   클래스안에 선언된 변수나 메서드를 사용하려면 해당 클래스타입으로 참조변수를 선언해야      한다.

   3. 연관성있는 저장공간과 기능을 한곳에 묶어줄 수 있다.
   저장공간과 기능을 나누어 관리하게 되면 코드가 길어졌을 때 사용하기 불편하다
   이 때 클래스로 연관성있는 저장공간과 기능을 묶어서 관리하면 편리하다.

## 클래스 선언
class 클래스명{
   변수 // 멤버변수,전역변수,필드

   메서드 // 멤버메서드

   class를 구성하는 모든변수,메서드를 통틀어서 해당클래스 멤버라고 부른다.
}

## 인스턴스화
   클래스(설계도)를 이용해 객체를 찍어내는 작업
   // 클래스를 메모리에 할당하는 작업

   클래스명 참조변수명 = new 생성자;
   Student st1 = new Student();

## 생성자(Constructer)
   1. 클래스 이름뒤에 소괄호가 있는 형태
   2. 생성자는 메서드와 비슷하지만 메서드라고 부르지 않고 생성자라고 부른다.
   3. 생성자는 리턴이라는 개념이 없다.
   4. 객체를 생성할때 반드시 한번 실행되는 기능이다.
   5. 기본생성자와 매개변수 생성자가 존재한다.
   6. 매개변수 생성자는 주로 해당 객체의 필드값을 초기화하기위해 사용한다.


## 기본생성자
클래스명(){

}
1. 매개변수를 받지않는 생성자
2. 클래스 선언 시 자동으로 생성되며 사용자가 직접 생성자를 구현하게 되면
   자동으로 만들어놓은 기본생성자는 없앤다.

## 매개변수 생성자
1. 매개변수를 받는 생성자
2. 주로 객체의 속성값을 초기화하는 기능을 목적으로 사용한다.

## this
   객체 자기 자신을 의미한다. <= 객체 자기 자신의 주소값을 담은 변수이다.
   객체의 주소값을 담고있기 때문에 this.멤버명 <= 해당객체의 멤버에 접근할 수 있다.

## 객체 배열(Object Array)
   배열의 요소로 객체를 가지는 배열
   배열의 각 저장공간에 객체들의 주소값이 들어있다.
   배열의 타입을 클래스와 맞춰줘야한다.

## 2차원 배열
   1. 배열안에 요소로 배열을 저장하는 형태
   2. 1차원 배열이 선형구조였다면 2차원 배열은 평면구조이다.
   3. 2차원 배열은 주로 모든 요소에 접근할때 2중 for문을 사용한다ㅏ.

## 2차원 배열 선언방법
   자료형 [][] 배열명 = new 자료형[배열의 세로크기][배열의 가로크기];
   int [][] arr = new int[2][3];

## 2차원 배열 선언과 동시에 초기화
   자료형[][] 배열명 = {
      {값1,값,...},
      {값1,값2,...},
      {값1,값2,...}
   };

   int[][] arr = {
      {10,20,30},
      {40,50,60}
   };

## 2중 for문
   for문안에 for문이 있는 형태
   반복을 반복시키는 형태

for(int i=0; i<10; i++){
   for(int j=0;j<10;j++){
      // 반복 실행할 코드
   }
}
1. 안쪽 for문의 초기식 변수가 바깥 for문의 초기식 변수이름과 같을 수 없다!
2. 안쪽 for문의 반복이 모두 끝나야 바깥 for문의 반복이 1번 처리된 것이다.































