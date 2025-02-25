<ul>
<li>HTML 요소에서 특정 <strong>속성과 값</strong>을 가진 요소를 선택할 때 사용</li>
<li><code>input[속성명=속성값]</code></li>
</ul>
<pre><code class="language-html">&lt;style&gt;
 /* input 요소 중 type 속성이 &quot;password&quot;인 요소 선택 */
 input[type=&quot;password&quot;] {
  width: 100%;
 }

 /* input 요소 중 placeholder 속성이 &quot;아이디를 입력하세요.&quot;인 요소 선택 */
 input[placeholder=&quot;아이디를 입력하세요.&quot;] {
  color: red !important;
 }

 input[placeholder=&quot;아이디를 입력하세요.&quot;] {
  color: purple; /* !important가 적용된 스타일이 우선됨 */
 }
&lt;/style&gt;

...

&lt;body&gt;
 &lt;input type=&quot;text&quot; name=&quot;id&quot; placeholder=&quot;아이디를 입력하세요.&quot;&gt;
 &lt;input type=&quot;password&quot; name=&quot;password&quot; placeholder=&quot;비밀번호를 입력하세요.&quot;&gt;
 &lt;button&gt;버튼&lt;/button&gt;
&lt;/body&gt;</code></pre>
<blockquote>
<h3 id="❗-important-주의사항">❗ !important 주의사항</h3>
<p>•    <strong>CSS 우선순위</strong>에서 가장 높음 → 나중에 작성한 스타일도 덮어버림
•    <strong>유지보수 어려움</strong> → 다른 스타일 적용이 어려워질 수 있음
•    <strong>가급적 사용 지양</strong> → 꼭 필요한 경우에만 사용</p>
</blockquote>
<h3 id="✅-속성-선택자-종류-정리"><strong>✅ 속성 선택자 종류 정리</strong></h3>
<table>
<thead>
<tr>
<th>선택자</th>
<th>설명</th>
<th>예제</th>
</tr>
</thead>
<tbody><tr>
<td><code>[속성]</code></td>
<td>해당 속성이 있는 모든 요소 선택</td>
<td><code>input[disabled]</code></td>
</tr>
<tr>
<td><code>[속성=&quot;값&quot;]</code></td>
<td>특정 속성과 값이 일치하는 요소 선택</td>
<td><code>input[type=&quot;text&quot;]</code></td>
</tr>
<tr>
<td><code>[속성~=&quot;값&quot;]</code></td>
<td>값이 단어 목록 중 하나로 포함된 요소 선택</td>
<td><code>div[class~=&quot;box&quot;]</code></td>
</tr>
<tr>
<td><code>[속성^=&quot;값&quot;]</code></td>
<td>값이 특정 문자열로 <strong>시작</strong>하는 요소 선택</td>
<td><code>input[name^=&quot;user&quot;]</code></td>
</tr>
<tr>
<td><code>[속성$=&quot;값&quot;]</code></td>
<td>값이 특정 문자열로 <strong>끝</strong>나는 요소 선택</td>
<td><code>img[src$=&quot;.png&quot;]</code></td>
</tr>
<tr>
<td><code>[속성*=&quot;값&quot;]</code></td>
<td>값이 특정 문자열을 <strong>포함</strong>하는 요소 선택</td>
<td><code>a[href*=&quot;naver&quot;]</code></td>
</tr>
</tbody></table>