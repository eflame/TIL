제어문
1. 조건문
	- if문
	- switch문
	switch(변수명){
	case 값1:
		실행할 문장;
		break;
	case 값2:
		실행할 문장;
		break;
	......
	default:
		실행할 문장;
		break;
	}

2. 반복문
- for 문
	for(초기식; 조건식; 증감식){
		실행할 문장;
	}
	
	초기식 : 처음에 설정할 값을 지정하는 식
	조건식 : 조건이 true면 영역안에 문장을 실행시키고 false면 for문을 탈출
	증감식 : 값을 증가 or 감소 시키는 식

- while 문
	while(조건식 {
		실행할 문장;
	}	

for문 과 while문 비교
	- for : 몇 번 반복할지 알 때
	- while : 몇 번 반복할지 모를 때

do ~ while 문
	while과 동일하지만 최소 한 번은 무조건 실행해야 할 때 사용한다.
	
	do {
		실행할 문장;
	} while(조건식);

기타 제어문
	break : 즉시 해당 중괄호 영역을 탈출한다.
	continue : 즉시 다음 반복으로 넘어간다.

