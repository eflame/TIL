## mapper 쿼리 정의 및 단위 테스트
MemberJoinDTO
memberId, loginId, password, name, age 

mapper.xml > mapper.java > mapperTest.java 끝
<br/>
insertMember, selectMemberId
<br/>
단건 Optional<Long> selectMemberId

----
@SpringBootTest
@Transactional

@Autowired MemberMapper memberMapper;
test > gwt 

insertMember

selectMember

assertThat()

## service
MemberService.java

@Service
@Transactional
@RequiredArgsConstructor

priavte final MemberMapper membberMapper;

```JAVA
addMember(MemberJoinDTO memberJoinDTO) {
  memberMapper.insertMember(memberJoinDTO);
}
```

```JAVA
findMemberId(String loginId, String password) {
  return memberMapper.selectMember(logindId, password);
}
```
-----------------------------

## Service 테스트 Mockito & 스터빙
@Extendwith(MockitoExtension.class)

@Mock 
MemberMapper memberMapper; 가짜 생성

@InjectMocks
MemberService memberService;

test > gwt > 스터빙

addMember
//g
Mockito.doReturn()
반환 doRetrun
doNothing().when(memberMapper).insertMember(any());
//w
memberService.addMember(MemberJoinDTO.builder().buil());
//t 반환 없다면 몇번실행 확인
verfy(memberMapper, times(1)).insertMember(any());

findMemberId
//g
doReteturn(Optional.of(1L)).when(memberMapper).selectMemberId(any(), any());
//w
memberService.findMemberId("test", "1234");
//t
asserThat(memberId).isEqualTo(1L);

-------------------------------------------

## Controller

@Controller
@RequestMapping("/member")
@RequiredArgsConstructor

```
@GetMapping("join")
public String join() {
  return "member/join";
}
```

```
@PostMapping("join")
public String join(MemberJoinDTO memberJoinDTO) {
  memberService.addMember(memberJoinDTO);

  return "member/login";
}
```

```
@GetMapping("login")
public String login() {
  return "member/login";
}
```

```
@PostMapping("login")
public String login(String loginId, String password,
                      Httpsession session) {
  Long memberId = memberService.findMemberId(loginId, password);

  session.setAttribute("memberId", memberId);

  return "main";
}
```











