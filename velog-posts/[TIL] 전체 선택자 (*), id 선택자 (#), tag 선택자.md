<h3 id="전체-선택자-">전체 선택자 (*)</h3>
<pre><code class="language-html"> &lt;style&gt;
  * {
   color: blue;
  }
 &lt;/style&gt;

...

&lt;body&gt;

 &lt;h1&gt;전체 선택자&lt;/h1&gt;
 &lt;h2&gt;전체 선택자의 기로 (*)&lt;/h2&gt;
 &lt;p&gt;전체 선택자는 asterisk (*) 기호를 사용하며, 우선순위가 가장 낮은 선택자이다.  &lt;/p&gt;

&lt;/body&gt;</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/d450d980-fe62-4e2d-999e-3bfc76d07934/image.png" /></p>
<h3 id="id-선택자-">id 선택자 (#)</h3>
<pre><code class="language-html"> &lt;style&gt;
  #container {
   width: 400px;
   height: 400px;
   background-color: purple;
  }
 &lt;/style&gt;
 ...
 &lt;body&gt;
 &lt;h1&gt;아이디 선택자(#)&lt;/h1&gt;
 &lt;p&gt;아이디 선택자는 웹 문서에 단 하나만 존재하는 선택자이다. &lt;/p&gt;
 &lt;p&gt;우선순위가 가장 높은 선택자이다.&lt;/p&gt;
 &lt;p&gt;만약 속성의 id=&quot;name&quot;이라면 #name으로 호출한다. &lt;/p&gt;

 &lt;div id=&quot;container&quot;&gt;&lt;/div&gt;
&lt;/body&gt;</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/96c8211f-09f4-44f4-ad58-97aa3f2edd1f/image.png" /></p>
<h3 id="tag-선택자">tag 선택자</h3>
<pre><code class="language-html"> &lt;style&gt;
  h1 {
   font-size: 100px;
  }
  p {
   font-size: 10px;
  }
 &lt;/style&gt;
 ...
 &lt;body&gt;
 &lt;h1&gt;태그 선택자&lt;/h1&gt;
 &lt;p&gt;특정 태그를 사용한 요소에 스타일을 적용할 수 있는 선택자이다. &lt;/p&gt;
 &lt;p&gt;
  전체 선택자 다음으로 많은 요소들에 스타일을 적용하는 태그 선택자 tag selector는 &lt;br /&gt;
  특정 태그가 쓰인 모든 요소에 스타일을 적용한다. 
 &lt;/p&gt;
&lt;/body&gt;</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/347d287a-f8cd-467b-b1ed-8d7f68450255/image.png" /></p>