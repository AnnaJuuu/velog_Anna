<h3 id="androidid">Android:id</h3>
<p>id를 알아보기 쉽게 변경해주기 (자료형_닉)</p>
<img src="https://velog.velcdn.com/images/a700hui/post/2dc3651e-f3df-4bbb-ad17-0205231ce29e/image.png" width="40%" />

<hr />
<h3 id="chain">Chain</h3>
<ul>
<li><p>Chain은 ConstraintLayout에서 사용할 수 있는 기능으로 양방향의 위치를 제한하여 서로 연결된 View Group을 만들 수 있다.</p>
</li>
<li><p>Chain linear group은 Spread, Spread inside, packed 세가지 속성으로 다음 사진처럼 제어할 수 있다.</p>
</li>
</ul>
<img src="https://velog.velcdn.com/images/a700hui/post/2019f397-5394-4861-9702-cb95ec4c94dc/image.png" width="60%" />

<p><strong><code>spread</code></strong> 속성은 일정한 간격으로 버튼들을 배치합니다.</p>
<p><strong><code>packed</code></strong> 속성은 버튼들을 모아줍니다. </p>
<p><strong><code>spread_inside</code></strong> 속성은 버튼들을 가능한 최대한 일정한 간격으로 떨어트립니다. </p>
<p>Create Horizontal Chain &gt; Horizontal Chain Style</p>
<img src="https://velog.velcdn.com/images/a700hui/post/04481b34-9bb4-4099-b0af-c29c970c3068/image.png" width="60%" />
<img src="https://velog.velcdn.com/images/a700hui/post/e22cea2f-e9c3-4138-9302-aeb925f1e21f/image.png" width="60%" />

<hr />
<h3 id="center">Center</h3>
<p><code>gravity</code>속성은 뷰그룹 내의 내용물을 정렬하는 속성으로 center이외도 저희가 잘 아는 left, right등이 있다. </p>
<img src="https://velog.velcdn.com/images/a700hui/post/e4cbf5e5-3e5d-4184-9882-198ce1bb7999/image.png" width="30%" />
<img src="https://velog.velcdn.com/images/a700hui/post/1ccfd0b8-4cd3-45dc-8672-cfc2bde46ead/image.png" width="30%" />
<img src="https://velog.velcdn.com/images/a700hui/post/b806b3e1-b599-421d-b721-4520fe76c117/image.png" width="30%" />

<hr />
<h3 id="resultactivity">ResultActivity</h3>
<p>BMI 메인화면 구성 완료 후 그 다음 결과 페이지를 만들어야한다. 
페이지 새로 만드는 방법은 다음과 같다.</p>
<img src="https://velog.velcdn.com/images/a700hui/post/47e94f37-e649-493e-a3c6-a2b8eb1ae89a/image.png" width="50%" />
MainActivity를 우클락
<img src="https://velog.velcdn.com/images/a700hui/post/5cff25d0-cd31-480a-9892-c2a21014fca5/image.png" width="60%" />

<p>사진 오른쪽 아래에 나온 항목들이 처음에 프로젝트 생성할 때랑 같은 뷰들이 있다. </p>
<hr />
<h3 id="findviewbyid">findViewById&lt;&gt;()</h3>
<p>findViewById&lt;어디서&gt;(R.id.아이디 이름) &gt;&gt; 어디서 : 아이디 타입
et_height가 변수 heightEditText와 연결함</p>
<pre><code class="language-kotlin">val heightEditText = findViewById&lt;EditText&gt;(R.id.et_height)
val weightEditText = findViewById&lt;EditText&gt;(R.id.et_weight)
val submitButton = findViewById&lt;Button&gt;(R.id.btn_check)</code></pre>
<h3 id="예외-처리toast">예외 처리,Toast</h3>
<pre><code class="language-kotlin">//btn_check 눌렀을 때 위 데이터들 넘겨주기
submitButton.setOnClickListener {

//데이터 입력하지 않고 확인 버튼을 눌렀을 때 예외처리 해주기
if(heightEditText.text.isEmpty())    //heightEditText여기에 있는 text가 비어있을 때
{

//Toast.makeText(context, text, 유지 시간)
//신장 값을 입력 안하면 &quot;신장을 입력해주세요&quot;라고 화면에 뜬다.
Toast.makeText(this, &quot;신장을 입력해주세요!&quot;, Toast.LENGTH_SHORT).show()

//아래 부분이 실행하면 안되기 때문에 리턴해야 한다.
return@setOnClickListener
}

if(weightEditText.text.isEmpty())
{
Toast.makeText(this, &quot;체중을 입력해주세요!&quot;, Toast.LENGTH_SHORT).show()
return@setOnClickListener
}
</code></pre>
<h3 id="intent">Intent</h3>
<pre><code class="language-kotlin">//heightEditText에서 받아온 문자열을 숫자로 바꿔서 height에 넣기
val height : Int = heightEditText.text.toString().toInt()
val weight : Int = weightEditText.text.toString().toInt()

//액티비티에서 액티비티로 데이터 전송할 때는 intent를 사용한다.
val intent = Intent(this, ResultActivity::class.java)
//사용자가 입력한 키와 몸무게를 넘겨줄거다.
intent.putExtra(&quot;height&quot;, height)
intent.putExtra(&quot;weight&quot;, weight)
//mainActivity에서 ResultActivity를 부른거다.
startActivity(intent)</code></pre>