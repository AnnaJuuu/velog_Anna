<h3 id="table">table</h3>
<ul>
<li>table은 행<code>row</code>과 열<code>column</code> 로 구성된 데이터 집합이다.</li>
</ul>
<table>
<thead>
<tr>
<th><strong>태그</strong></th>
<th><strong>비고</strong></th>
</tr>
</thead>
<tbody><tr>
<td><code>&lt;table&gt;</code></td>
<td>테이블을 만드는 태그</td>
</tr>
<tr>
<td><code>&lt;th&gt;</code></td>
<td>헤더부분 셀</td>
</tr>
<tr>
<td><code>&lt;tr&gt;</code></td>
<td>행을 만드는 태그</td>
</tr>
<tr>
<td><code>&lt;td&gt;</code></td>
<td>열을 만드는 태그</td>
</tr>
</tbody></table>
<h4 id="셀-합치기">셀 합치기</h4>
<pre><code class="language-html">&lt;!-- 행 합치기 --&gt;
&lt;td rowspan=&quot;합칠 개수&quot;&gt;
&lt;!-- 열 합치기 --&gt;
&lt;td colspan=&quot;합칠 개수&quot;&gt;</code></pre>
<h3 id="실습">실습</h3>
<pre><code class="language-html"> &lt;table border=&quot;1&quot;&gt;
  &lt;tr&gt;
   &lt;th&gt;이름&lt;/th&gt;
   &lt;th&gt;나이&lt;/th&gt;
  &lt;/tr&gt;

  &lt;tr&gt;
   &lt;td&gt;주혜령&lt;/td&gt;
   &lt;td&gt;20&lt;/td&gt;
  &lt;/tr&gt;

  &lt;tr&gt;
   &lt;td&gt;홍길동&lt;/td&gt;
   &lt;td&gt;17&lt;/td&gt;
  &lt;/tr&gt;
 &lt;/table&gt;</code></pre>
<img src="https://velog.velcdn.com/images/a700hui/post/cb550c8f-6f6e-485c-a514-9fa4e35eea1d/image.png" width="20%" /> 


<pre><code class="language-html"> &lt;table border=&quot;1&quot;&gt;
  &lt;tr&gt;
   &lt;td colspan=&quot;2&quot;&gt;1&lt;/td&gt;
   &lt;td rowspan=&quot;2&quot;&gt;3&lt;/td&gt;
   &lt;td&gt;4&lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td&gt;5&lt;/td&gt;
   &lt;td&gt;6&lt;/td&gt;
   &lt;td&gt;8&lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td&gt;9&lt;/td&gt;
   &lt;td colspan=&quot;3&quot;&gt;0&lt;/td&gt;
  &lt;/tr&gt;
 &lt;/table&gt;</code></pre>
<img src="https://velog.velcdn.com/images/a700hui/post/8655a51d-078e-4068-8231-20f024410dfe/image.png" width="20%" />