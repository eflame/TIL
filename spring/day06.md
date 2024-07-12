# Mockito 란?
- mock 객체를 만들고 mock의 행동을 정의하는 stubbing과 작동하는지에 대한 검증을 할 수 있는 verify등 다양한 기능을 제공해주는 프레임워크

# Mock 객체란?
- 어떤 객체를 모방하는 가짜 객체이다.
- 껍데기만 있으면 내부 구현부는 존재하지 않는다.
  즉, Mock객체의 메서드를 실행하여도 아무일도 일어나지 않는다.
- Mock객체를 만드는 것을 Mocking이라고 한다.

# JUnit에서 Mockito사용하기
- JUnit과 Mockito는 둘 다 프레임워크이기 때문에 서로 결합하여 사용하기 위해 추가 설정이 필요하다.
- JUnit5에서는 @ExtendWith(MockitoExtenstion.class) 를 사용해야 기능이 확장된다.

# Mockito에서 지원하는 주요 어노테이션
- @Mock : Mock 객체를 만들어준다.
- @InjectMocks : Mock객체를 주입해준다.


