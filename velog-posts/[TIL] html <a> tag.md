<h3 id="a태그">a태그</h3>
<p>하이퍼링크를 연결해주는 태그</p>
<ul>
<li>타 웹사이트로 이동</li>
</ul>
<p><code>//</code> 프로토콜 (절대경로)</p>
<pre><code class="language-html"> &lt;a href=&quot;//www.naver.com&quot;&gt;naver로 이동!&lt;/a&gt;</code></pre>
<ul>
<li>외부 페이지 이동</li>
</ul>
<pre><code class="language-html">&lt;a href=&quot;./mail.html&quot;&gt; 메일 페이지로 이동! &lt;/a&gt;</code></pre>
<ul>
<li>페이지 내 이동</li>
<li>아이디 속성을 #으로 표현한다.</li>
</ul>
<pre><code class="language-html"> &lt;a href=&quot;#nav&quot;&gt;페이지 내에서 이동(북마크)&lt;/a&gt; &lt;!-- 클릭하면 --&gt;
 &lt;div style=&quot;height: 5000px; background-color: green;&quot;&gt;여기가 DIV&lt;/div&gt;
 &lt;div id=&quot;nav&quot;&gt;&lt;/div&gt; &lt;!-- 맨 아래로 찾아간다 --&gt; </code></pre>
<h4 id="target-속성">target 속성</h4>
<p>_self : 현재 페이지 (기본값) 
_blank : 새 탭
_parent : 부모 페이지로 이동, iframe 사용시 잘안씀
_top : 부모 페이지로 이동, iframe 사용시 잘안씀</p>
<img src="https://velog.velcdn.com/images/a700hui/post/9d45a7b9-35d6-454b-9947-936d5ce3f6bd/image.png" width="20%" /> 

<pre><code class="language-html">&lt;a href=&quot;//www.naver.com&quot; target=&quot;_blank&quot;&gt;naver로 이동!&lt;/a&gt;</code></pre>
<h3 id="실습">실습</h3>
<p>1) 아이콘 2개, icon4번과 icon1번을 불러온다.
2) 아이콘을 클릭하면 각각 알맞는 페이지로 이동한다.
3) icon4번을 클릭하면 day02에 index.html로 이동한다.
4) icon1번을 클릭하면 카카오프렌즈샵으로 이동한다.</p>
<pre><code class="language-html"> &lt;a href=&quot;/day02/index.html&quot;&gt;
  &lt;img src=&quot;images/img01/icon04.png&quot; alt=&quot;아이콘 4&quot;&gt;
 &lt;/a&gt;
 &lt;a href=&quot;https://store.kakao.com/kakaofriends&quot;&gt;
  &lt;img src=&quot;images/img01/img02/icon01.png&quot; alt=&quot;아이콘 1&quot;&gt;
 &lt;/a&gt;</code></pre>