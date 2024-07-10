
```
@RestController // 레스트 컨트롤러
@RequiredArgsConsructor
public class BoardApi {
  private final BoardService boardService;

  @GetMapping("/v1/board/{boardId}")
  publick BoardDTO getBoard(@PathVariable("boardId") Long boardId,
                        @RequestParam("category") String category) {
        BoardDTO boardDTO = new BoardDTO;
        boardDTO
    return boardDTO;
  }
}
``
