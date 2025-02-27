<h3 id="css란">CSS란?</h3>
<ul>
<li>CSS란 Cascading Style Sheets의 약자</li>
<li>CSS는 HTML 요소들이 각종 미디어에서 어떻게 보이는 가를 정의하는데 사용한다.</li>
<li>스타일을 HTML문서로부터 분리하는 것이 가능해진다.</li>
</ul>
<h3 id="css를-사용하는-이유">CSS를 사용하는 이유</h3>
<ul>
<li>HTML만으로 웹 페이지를 제작할 경우, HTML 요소의 세부 스타일을 일일이 따로 지정해주어야 하기 때문에 많은 시간이 걸리며, 완성한 후에도 스타일의 변경 및 유지보수가 매우 힘들어진다.</li>
<li>이 문제점을 해소하기 위해서 W3C에서 만든 스타일 시트 언어가 바로 <code>CSS</code>이다.</li>
<li>웹 페이지의 스타일을 별도의 파일로 저장할 수 있게 해줌으로서 사이트의 전체 스타일을 손쉽게 제어할 수 있게 된다.</li>
<li>또한 웹 사이트의 스타일을 일관성 있게 유지할 수 있도록 해주며, 그에 따른 유지보수 또한 쉬워진다.</li>
</ul>
<h3 id="css문법">CSS문법</h3>
<pre><code class="language-html">p { text-align: center; color: blue; }
[선택자] { [속성명]:[속성값]; [속성명]:[속성값]; }</code></pre>
<h3 id="css의-선언부">CSS의 선언부</h3>
<p>1) CSS의 문법은 선택자와 선언부로 구성된다.</p>
<p>2) 선택자는 CSS를 적용하고자 하는 HTML 요소를 가리키고, 선언부는 중괄호<code>{}</code>를 사용하여 전체를 둘러 싼다</p>
<p>3) 각 선언은 CSS 속성명과 속성 값을 클론<code>:</code>으로 연결한다.</p>
<p>4) CSS 선언은 언제나 마지막에 세미클론<code>;</code>으로 끝마친다.</p>
<h3 id="css의-선택자">CSS의 선택자</h3>
<h4 id="1-전체-선택자">1) 전체 선택자</h4>
<ul>
<li>스타일을 <strong>모든 요소에 적용</strong>할 때 사용한다.</li>
<li>주로 모든 하위 요소에 한꺼번에 스타일을 적용할 때 사용하고 전체 선택자는 asterisk<code>*</code> 기호를 사용한다.</li>
</ul>
<h4 id="2-태그-선택자">2) 태그 선택자</h4>
<ul>
<li><strong>특정 태그가 쓰인 모든 요소</strong>에 스타일을 적용한다.</li>
<li>선택자 위치에 <code>태그명</code>을 작성하면 사용된 모든 해당 태그에 동일한 스타일이 적용된다.</li>
</ul>
<h4 id="3-클래스-선택자class-속성에-작성된-값">3) 클래스 선택자(class 속성에 작성된 값)</h4>
<ul>
<li>클래스 선택자는 <strong>특정 집단의 여러 요소</strong>를 한 번에 선택할 때 사용한다.</li>
<li>같은 클래스 1을 가지는 요소들을 모두 선택해주고 스타일 적용 시 선택자에 <code>.클래스명</code>을 작성한다.</li>
</ul>
<h4 id="4-아이디-선택자id-속성에-작성된-값">4) 아이디 선택자(id 속성에 작성된 값)</h4>
<ul>
<li>아이디 선택자는 <strong>특정 요소를 선택</strong>할 때 사용한다.</li>
<li>스타일을 지정할 때 사용되며, 선택자 부분에 <code>#아이디명</code>을 작성한다.</li>
</ul>
<h4 id="5-그룹-선택자">5) 그룹 선택자</h4>
<ul>
<li><strong>여러 선택자에 같은 스타일을 적용</strong>할 경우 쉼표<code>,</code>로 구분해서 여러 선택자를 나열한 후 스타일은 한 번만 정의한다.</li>
</ul>