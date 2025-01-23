<h3 id="form-요소">form 요소</h3>
<ul>
<li>웹페이지에서 내 정보를 서버로 보내거나 혹은 서버로 보내지 않더라도 자체 웹페이지에서 사용자와 상호작용을 하기 위해 입력값이나 버튼과 같은 이벤트 요소가 필요할 때 사용되는 HTML의 <code>from</code>태그다.</li>
<li>폼 요소는 자체적으로 양식을 생성하는 것이 아니라 <code>inpout</code>, <code>label</code> 들과 같은 필수 양식 요소를 포함하는 컨테이너이다.</li>
</ul>
<table>
<thead>
<tr>
<th><strong>Tag</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody><tr>
<td><code>&lt;form&gt;</code></td>
<td>사용 측에서 입력을 입력하는 HTML 양식을 정의</td>
</tr>
<tr>
<td><code>&lt;fieldset&gt;</code></td>
<td>관련 요소를 양식으로 그룹화</td>
</tr>
<tr>
<td><code>&lt;legend&gt;</code></td>
<td><code>&lt;fieldset&gt;</code> 요소에 대한 캡션을 정의</td>
</tr>
<tr>
<td><code>&lt;input&gt;</code></td>
<td>입력 컨트롤을 정의</td>
</tr>
<tr>
<td><code>&lt;label&gt;</code></td>
<td>입력 요소의 레이블을 정의</td>
</tr>
<tr>
<td><code>&lt;textarea&gt;</code></td>
<td>다중 라인 입력 컨트롤을 정의</td>
</tr>
<tr>
<td><code>&lt;select&gt;</code></td>
<td>드롭다운 목록을 정의</td>
</tr>
<tr>
<td><code>&lt;optgroup&gt;</code></td>
<td>드롭다운 목록에서 관련 옵션 그룹을 정의</td>
</tr>
<tr>
<td><code>&lt;option&gt;</code></td>
<td>드롭다운 목록에서 옵션을 정의합</td>
</tr>
<tr>
<td><code>&lt;button&gt;</code></td>
<td>클릭 가능한 버튼을 정의합</td>
</tr>
</tbody></table>
<h3 id="input-태그">input 태그</h3>
<ul>
<li>사용자가 정보를 입력하는 부분을 만들어야할 때 사용</li>
<li>name과 value (속성)
<code>name</code> : form태그 내에서 input의 속성의 이름으로, 백엔드에서 값을 찾기위한 목적으로 사용된다.
<code>value</code> : form태그에서 사용자에게 입력받은 데이터이다.</li>
</ul>
<table>
<thead>
<tr>
<th><strong>input 속성</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>readonly</strong></td>
<td>읽기 전용 필드로 만들기</td>
</tr>
<tr>
<td><strong>placeholder</strong></td>
<td>힌트 표시(필드 클릭시 내용 사라짐)</td>
</tr>
<tr>
<td>autofocus</td>
<td>페이지를 불러오자 마자 특정 부분에 마우스 커서가 표시되도록 하는 것</td>
</tr>
<tr>
<td>autocomplete</td>
<td>자동완성 설정</td>
</tr>
<tr>
<td>max / min</td>
<td><code>&lt;input&gt;</code> 필드의 최대값과 최소값 지정</td>
</tr>
<tr>
<td><strong>maxLength</strong></td>
<td>텍스트 필드에 최대로 입력할 수 있는 문자의 개수 지정</td>
</tr>
<tr>
<td>step</td>
<td>숫자의 간격 설정 <br /><code>&lt;input&gt;</code> 이 date, datetime, datetime-local, month, week,time, number, range일 경우만 사용가능</td>
</tr>
<tr>
<td><strong>required</strong></td>
<td>필수 입력 필드 지정(빈칸이면 안 넘어감)</td>
</tr>
<tr>
<td><strong>type ⭐</strong></td>
<td>input 태그의 타입을 지정단순히 텍스트입력창인지 이메일, 전화번호 양식 혹은 파일첨부, 동영상 첨부 인지</td>
</tr>
<tr>
<td>name</td>
<td>컨트롤의 이름을 난타낸다. 양식이 제출될 때 이 이름이 컨트롤을 식별하는데 사용됨.</td>
</tr>
</tbody></table>
<pre><code class="language-html">      &lt;!-- 버튼 --&gt;
      &lt;fieldset&gt;
        &lt;legend&gt;button&lt;/legend&gt;
        &lt;input type=&quot;button&quot; value=&quot;버튼&quot; /&gt;
        &lt;input type=&quot;reset&quot; value=&quot;초기화&quot; /&gt;
        &lt;input type=&quot;submit&quot; value=&quot;전송&quot; /&gt;
      &lt;/fieldset&gt;</code></pre>
<img src="https://velog.velcdn.com/images/a700hui/post/3a79f579-6a12-4bcc-ab2e-90964eae589a/image.png" width="30%" /> 



<pre><code class="language-html">      &lt;!-- 파일 추가 --&gt;
      &lt;fieldset&gt;
        &lt;legend&gt;file&lt;/legend&gt;
        &lt;input type=&quot;file&quot; /&gt;
      &lt;/fieldset&gt;</code></pre>
<img src="https://velog.velcdn.com/images/a700hui/post/1d31a688-39d6-4c46-a578-76d989786ae2/image.png" width="30%" /> 

<pre><code class="language-html">      &lt;!-- 기타 --&gt;
      &lt;fieldset&gt;
        &lt;legend&gt;other&lt;/legend&gt;
        &lt;p&gt;색상 &lt;input type=&quot;color&quot; /&gt;&lt;/p&gt;
        &lt;p&gt;이메일 &lt;input type=&quot;email&quot; style=&quot;width: 50px&quot; /&gt;&lt;/p&gt;
        &lt;p&gt;웹 사이트 &lt;input type=&quot;url&quot; /&gt;&lt;/p&gt;
        &lt;p&gt;연락처 &lt;input type=&quot;tel&quot; /&gt;&lt;/p&gt;
        &lt;p&gt;
          날짜 &lt;input type=&quot;datetime-local&quot; /&gt;&lt;br /&gt;
          날짜 &lt;input type=&quot;date&quot; /&gt;
        &lt;/p&gt;
        &lt;p&gt;
          참여 인원 &lt;input type=&quot;number&quot; value=&quot;1&quot; min=&quot;0&quot; max=&quot;100&quot; step=&quot;5&quot; /&gt;
        &lt;/p&gt;
        &lt;p&gt;단계(상, 중, 하) &lt;input type=&quot;range&quot; value=&quot;1&quot; min=&quot;1&quot; max=&quot;3&quot; /&gt;&lt;/p&gt;
      &lt;/fieldset&gt;</code></pre>
<img src="https://velog.velcdn.com/images/a700hui/post/2a9004a1-e46b-4c24-8641-8fce7a7c6439/image.png" width="40%" />