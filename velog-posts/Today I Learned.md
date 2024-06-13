<h2 id="✏240612-수요일-til">✏240612 수요일 TIL</h2>
<ul>
<li><h3 id="📖-오늘의-공부">📖 오늘의 공부</h3>
<ul>
<li>알고리즘 코드카타 - <a href="https://velog.io/@a700hui/%EB%82%98%EB%A8%B8%EC%A7%80%EA%B0%80-1%EC%9D%B4-%EB%90%98%EB%8A%94-%EC%88%98-%EC%B0%BE%EA%B8%B0"><strong>나머지가 1이 되는 수 찾기</strong></a> ✔️</li>
<li>kotlin 4주차 ✔️</li>
<li><a href="https://velog.io/@a700hui/%ED%9D%90%EB%A6%84%EC%9D%98-%EC%A4%91%EB%8B%A8%EA%B3%BC-%EB%B0%98%ED%99%98"><strong>프로그램의 프름의 제어</strong></a> ✔️</li>
<li><a href="https://velog.io/@a700hui/%EC%BA%A1%EC%8A%90%ED%99%94"><strong>캡슐화</strong></a> ✔️</li>
<li><a href="https://velog.io/@a700hui/%EC%A7%80%EC%97%B0-%EC%B4%88%EA%B8%B0%ED%99%94-1"><strong>지연 초기화와 위임</strong></a> ✔️<br />
</li>
</ul>
</li>
<li><h3 id="📖-오늘-배운-것">📖 오늘 배운 것</h3>
<ul>
<li><p>모듈로 연산하는 이유</p>
<ul>
<li>나머지 값을 이용해 자신의 입력 값에  해당하는 값이 들어오면 항상 0이 되는 특징이 있다.</li>
<li>배열에 원래 인덱스로 돌아오기위해 자주 사용!<br />
</li>
</ul>
</li>
<li><p>람다식에 있는 return문은 아래 조건 때문에 조건문 아닌 이 함수 자체에서 빠져 나간다. </p>
<pre><code class="language-kotlin">if(result &gt; 10) return  //10보다 크면 이 함수를 빠져 나감</code></pre>
<br />
</li>
<li><p>조건문에서만 빠져 나가고 싶으면 <strong>라벨@</strong> 사용하거나, <strong>익명 함수</strong>를 사용한다. </p>
<br />
</li>
<li><p>동일한 파일 내에 있는 메서드 안에서만! private class만! 호출 가능</p>
<ul>
<li>공개 메서드는 사용 가능한다.<br />
</li>
</ul>
</li>
<li><p>클래스에 주생성자가 있을 때만 아래코드가 가능한줄 알았는데, 주생성자가 없어도 사용 가능</p>
<pre><code class="language-kotlin">val person : Person by lazy {  
isPersonInstantiated = true  
Person(&quot;Kim&quot;, 23)  
}</code></pre>
<br />
</li>
<li><p>위임 변수 한 단계 더 들어가는 이유는 <strong>자바 게터, 세터</strong> 때문이다. </p>
<pre><code class="language-kotlin">val personDelegate = lazy {Person(&quot;Hong&quot;, 40) }
.
.
.
println(&quot;personDelegate.value.name = ${personDelegate.value.name}&quot;) </code></pre>
<br />
</li>
<li><p><strong>.isInitialized()</strong></p>
<ul>
<li>코틀린 표준 라이브러리에서 제공하는 함수로 지연 초기화 속성이 초기화되었는지 검사해 준다. 단, 이 함수를 선언할 때는 속성이 갖는 값이 아닌 참조를 전달해야 하므로 속성 이름 앞에 참조임을 나타내는 두 개의 콜론을 붙여야 함.<br /></li>
</ul>
</li>
</ul>
</li>
<li><h3 id="📖-느낀점">📖 느낀점</h3>
</li>
</ul>