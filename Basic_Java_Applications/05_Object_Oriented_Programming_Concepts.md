# 메소드
## 기능

<pre><code>
메소드 선언과 구현 (정의)

	리턴타입 메소드명(매개변수) <- 선언부
	{			    <- 구현부
		실행할 문장;
		return 리턴값;
	}
</code></pre>

1. 리턴타입 : 반환할 값이 있다면 반환 값의 자료형을 작성한다. 없다면 void를 작성한다.

2. 메서드명 : 가능하면 동사로 쩍는다.

3. 매개변수(parameter) : 메서드를 사용하는 쪽에서 전달받을 값이 있다면
			자료형과 순서에 맞게 선언해준다.

4. 실행할 문장 : 메서드의 기능을 구현하면 된다.

5. return : 생략이 가능하며 return이 실행되면 메서드가 종료된다.
	    리턴 값이 있다면 메서드를 호출한 부분을 통채로 리턴값으로 본다.
	    리턴이 없다면 값이 아니다.


메서드의 정의와 사용
1. 메서드를 정의할 때에는 {}가 있고, 반드시 메서드 밖에서 정의한다.
2. 메서드를 사용할 때에는 {}가 없고, 반드시 메서드 안에서 사용한다.


메서드의 정의 순서
1. 기능을 생각한다. (숫자를 더해주는 기능)
2. 반환타입이 생각나지 않는다면 우선 void로 작성한다.

<pre><code>
void
</code></pre>

3. 기능에 알맞은 메서드명을 작성한다.(가능하면 동사로)
	
<pre><code>
void add(){}
</code></pre>
  
4. 실행할 문장을 작성한다.

<pre><code>
void add(){
  int result = ? + ? ;
}
</code></pre>
  
5. 매개변수 생각한다. <br>

<pre><code>
void add(int num1, int num2){
  int result = num1 + num2;
}
</code></pre>

6. 리턴 값을 생각한다. <br>

<pre><code>
int add(int num1, int num2){
  int result = num1 + num2;
  return result;
}
</code></pre>

