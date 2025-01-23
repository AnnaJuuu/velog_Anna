<h3 id="datalist"><code>&lt;datalist&gt;</code></h3>
<ul>
<li>사용자가 쉽게 옵션을 <strong>선택</strong>하거나 데이터를 <strong>입력</strong>할 수 있도록 권장하는 선택지를 제공하는 용도로 사용됨</li>
<li>목록의 항목들은 <code>optione</code> 태그로 나타남</li>
</ul>
<pre><code class="language-html">  &lt;!-- 입력 또는 선택할 수 있음--&gt;
  &lt;fieldset&gt;
   &lt;legend&gt;datalist&lt;/legend&gt;
   &lt;input type=&quot;text&quot; name=&quot;studentDepartment&quot; list=&quot;list&quot; placeholder=&quot;학과명을 입력하세요.&quot;&gt;
   &lt;datalist id=&quot;list&quot;&gt;
    &lt;!-- 목록의 항목은 &lt;option&gt; 태그로 정의됩니다. --&gt;
    &lt;option value=&quot;컴퓨터공학과&quot;&gt;&lt;/option&gt;
    &lt;option value=&quot;영어영문과&quot;&gt;&lt;/option&gt;
    &lt;option value=&quot;경영학과&quot;&gt;&lt;/option&gt;
    &lt;option value=&quot;사회체육과&quot;&gt;&lt;/option&gt;
   &lt;/datalist&gt;
  &lt;/fieldset&gt;</code></pre>
<p>컴퓨터공학과를 선택해서 전송하면 value의 컴퓨터공학과가 실제값이고, name의 studentDepartment인 키를 담아 전송한다. </p>
<img src="https://velog.velcdn.com/images/a700hui/post/2843ef90-8e87-4c25-a0f5-3b033d0c0f44/image.png" width="30%" />

<hr />
<h3 id="select"><code>&lt;select&gt;</code></h3>
<ul>
<li>옵션 메뉴를 제공하는 컨트롤을 나타냄</li>
<li>사용자가 원하는 옵션을 선택할 수 있는 방법</li>
<li>드롭다운 목록, 셀렉트 박스</li>
<li>목록의 항목들은 <code>optione</code> 태그로 나타남</li>
</ul>
<pre><code class="language-html">      &lt;!-- 선택 사항 입력 불가 --&gt;
      &lt;fieldset&gt;
        &lt;legend&gt;select&lt;/legend&gt;
        &lt;select name=&quot;major&quot;&gt;
          &lt;option value=&quot;computer&quot;&gt;컴퓨터공학과&lt;/option&gt;
          &lt;option value=&quot;model&quot;&gt;모델학과&lt;/option&gt;
          &lt;option value=&quot;nurse&quot;&gt;간호학과&lt;/option&gt;
          &lt;option value=&quot;music&quot;&gt;실용음악과&lt;/option&gt;
        &lt;/select&gt;
      &lt;/fieldset&gt;</code></pre>
<p>컴퓨터공학과를 선택해서 전송하면 실제값인 computer가 key인 major에 담아 전송된다</p>
<img src="https://velog.velcdn.com/images/a700hui/post/95574270-3aee-4da4-9333-453761325081/image.png" width="20%" />