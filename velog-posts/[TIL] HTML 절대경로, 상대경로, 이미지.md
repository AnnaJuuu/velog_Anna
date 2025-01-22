<table>
<thead>
<tr>
<th>절대경로</th>
<th>상대경로</th>
</tr>
</thead>
<tbody><tr>
<td>시작위치부터 끝까지 전부 기입하는 방식</td>
<td>상대적인 경로 현재 폴더를 기준점으로 기입하는 경로 방식</td>
</tr>
</tbody></table>
<blockquote>
<p><code>/</code>    : 최상위 폴더의 경로</p>
<p><code>./</code>    : 현재 폴더의 경로</p>
<p><code>../</code> :  현재 폴더의 상위 폴더 경로</p>
</blockquote>
<h3 id="img">img</h3>
<pre><code class="language-html"> &lt;img src=&quot; &quot; alt=&quot;&quot;&gt;</code></pre>
<p><code>src</code> </p>
<ul>
<li>이미지 파일의 경로를 지정하는 속성</li>
<li>이미지가 저장된 위치(파일 경로 또는 URL)를 입력</li>
</ul>
<p><code>alt</code></p>
<ul>
<li>이미지가 로드되지 않거나 시각적으로 볼 수 없는 경우에 대신 표시되는 텍스트</li>
<li>또한, 화면 읽기 소프트웨어를 사용하는 사용자를 위해 대체 텍스트로 활용됨</li>
</ul>
<h3 id="실습">실습</h3>
<h4 id="파일-위치">파일 위치</h4>
<img src="https://velog.velcdn.com/images/a700hui/post/5323bd4f-ada3-4fb8-968e-a836a5d09daf/image.png" width="20%" /> 

<h4 id="코드">코드</h4>
<pre><code class="language-html">&lt;body&gt;
 &lt;img src=&quot;./images/icon02.png&quot; alt=&quot;아이콘2&quot;&gt;
 &lt;img src=&quot;/day03/images/img01/icon04.png&quot; alt=&quot;아이콘4&quot;&gt;
 &lt;img src=&quot;./images/img03/icon05.png&quot; alt=&quot;아이콘5&quot;&gt;
 &lt;img src=&quot;./images/img01/img02/icon01.png&quot; alt=&quot;아이콘1&quot;&gt;
 &lt;img src=&quot;./images/img01/img02/img04/icon03.png&quot; alt=&quot;아이콘3&quot;&gt;

 &lt;img src=&quot;/images/icon02.png&quot; alt=&quot;아이콘 2&quot;&gt;
&lt;/body&gt;</code></pre>
<h4 id="결과화면">결과화면</h4>
<img src="https://velog.velcdn.com/images/a700hui/post/3ce8b396-5264-44f2-a3fd-64c1b6560405/image.png" width="80%" />