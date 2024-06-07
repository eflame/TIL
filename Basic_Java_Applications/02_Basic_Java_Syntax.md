

## 제어문자 (Escape Character)
- 따옴표 안에서 사용되며, 미리 예약된 특수 기능을 하는 문자입니다.
- \(백슬래시, 역슬래시)를 사용합니다.

    - `\n` : 줄 바꿈
    - `\t` : 일정 간격을 띄워줍니다. (탭)
    - `\"` : 문자열 안에 큰 따옴표를 표현합니다.
    - `\'` : 문자열 안에 작은 따옴표를 표현합니다.
    - `\\` : 문자열 안에 백슬래시를 표현합니다.

## 출력 메서드 (Output Methods)
- 괄호 안에 있는 값을 콘솔에 출력합니다.

    - `println()` : 전달된 값을 출력하고 줄 바꿈을 수행합니다.
    - `print()` : 전달된 값을 출력하고 줄 바꿈을 하지 않습니다.
    - `printf()` : 형식에 맞는 값을 출력하고 줄 바꿈을 하지 않습니다.

### 출력 메서드의 목적
- 값을 확인하여 오류를 해결하는 데 사용됩니다.

## 함수 (Functions)
- 기능을 나타냅니다.
- 이름 뒤에 ()가 있습니다.

## 메서드 (Methods)
- 함수와 같습니다.
- 자바에서는 모든 함수를 클래스 내부에 만들기 때문에 메서드라고 합니다.

## 입력 메서드 (Input Methods)
- Scanner 클래스 내부에 입력 메서드가 있습니다.

    - `next()` : 입력을 String 타입으로 가져옵니다. 공백을 만날 때까지 입력을 가져옵니다.
    - `nextLine()` : 입력을 String 타입으로 가져옵니다. 한 줄 전체를 입력으로 가져옵니다. 공백을 포함합니다.