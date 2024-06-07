# 함수형 인터페이스(Functional Interface)
단 하나의 추상 메서드를 가지고 있는 인터페이스
@FunctionalInterface 라는 어노테이션을 명시해주면 하나의 추상 메서드만 선언할 수 있게 제한한다.

# 람다식(Lambda Expression) : 익명 메서드
자바 8버전부터 사용 가능하다.
메서드를 하나의 식으로 표현한다.
람다식을 매개변수로 전달 가능하며, 반환도 가능하다.

함수형 인터페이스는 추상 메서드가 한 개만 선언되기 때문에 람다식으로 재정의 할 때
메서드 이름이 필요 없다.

# 람다식 문법
```
(매개변수) -> { 바디 }
(int a, int b) -> { return a + b; }
(a, b) -> a + b
```

# 스트림(Stream)
- 배열, 컬렉션 같은 데이터 묶음을 편하고 효율적으로 처리하기 위해 제공되는 API
- 선언형(함수형) 프로그래밍을 자바로 구현해 놓은 클래스
- 람다를 활용할 수 있는 기술이다.
- 스트림은 값의 흐름을 의미한다.

# 선언형 프로그래밍이란?
- 명령형 프로그래밍 : 어떻게 할 것인가? ( 알고리즘 중 )
```
for(int i=0; i<ar.length; i++){
	System.out.println(ar[i] + 1);
}
```
- 선언형 프로그래밍 : 무엇을 할 것인가? (목표에 중점)
```
Arrays.stream(ar).forEach(num -> System.out.println(num1+1));
```
# 자바의 선언형 프로그래밍 지원
- JDK8부터 Stream과 Lambda를 지원한다.
- stream에서만 사용 가능한 메서드를 이용하여 프로그래밍 한다.
- 마치 블록을 조립하듯 메서드를 나열하여 프로그래밍한다.(메서드 체이닝)

# 스트림의 종류
- 기본타임 Stream
```
  IntStream    : int 타입의 테이터를 처리하기 위한 스트림
     DoubleStream : double 타입의             "    
       LongStream   : long 타입의             "
```
- 객체타입 Stream
  ```
	Stream<T> : T타입의 데이터를 처리하는 스트림
  ```

# 스트림의 3단계
1. 생성
- 범위를 이용한 생성(기본타입 스트림)
- Arrays를 이용한 생성
- Collection을 이용한 생성
2. 중간연산
- 반환타입이 stream 이다.
- 몇 번이든 사용 가능하다

3. 최종연산
- 반환 타입이 Stream이 아니다.
- 한 번만 사용 가능하다.

# 스트림 특징
1. Stream은 일회용이다. -> 재사용 불가
2. Stream은 원본 데이터를 수정하지 않는다.