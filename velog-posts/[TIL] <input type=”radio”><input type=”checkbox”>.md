<h3 id="input-typeradio"><code>&lt;input type=”radio”&gt;</code></h3>
<ul>
<li>같은 name 값을 가진 라디오 버튼들 중에서 <strong>하나만 선택</strong>할 수 있게 만듬</li>
<li>사용자가 선택한 값을 서버로 제출할 때, 이 name이 키(key)가 되어 값을 전달함</li>
</ul>
<pre><code class="language-html">&lt;!-- 개별 선택 --&gt;
&lt;fieldset&gt;
    &lt;legend&gt;관심이 있는 웹 개발 언어를 선택하세요.&lt;/legend&gt;
    &lt;div&gt;
       &lt;input type=&quot;radio&quot; id=&quot;html&quot; name=&quot;interest&quot; value=&quot;html&quot;&gt;
       &lt;label for=&quot;html&quot;&gt;HTML&lt;/label&gt;
    &lt;/div&gt;
    &lt;div&gt;
       &lt;input type=&quot;radio&quot; id=&quot;css&quot; name=&quot;interest&quot; value=&quot;interest&quot;&gt;
       &lt;label for=&quot;css&quot;&gt;CSS&lt;/label&gt;
    &lt;/div&gt;
    &lt;div&gt;
       &lt;input type=&quot;radio&quot; id=&quot;js&quot; name=&quot;interest&quot; value=&quot;interest&quot;&gt;
       &lt;label for=&quot;js&quot;&gt;JavaScript&lt;/label&gt;
    &lt;/div&gt;
&lt;/fieldset&gt;</code></pre>
<ul>
<li>사용자가 ‘HTML’을 선택하면, 해당 라디오 버튼의 값만 전송됨 <code>gender=html</code></li>
</ul>
<hr />
<h3 id="input-typecheckbox"><code>&lt;input type=”checkbox”&gt;</code></h3>
<ul>
<li>단일한 값으로 체크와 취소를 번갈아가며 할 수 있는 커트롤</li>
</ul>
<pre><code class="language-html">&lt;label for=&quot;opt-in&quot;&gt;이메일 수신 동의&lt;/label&gt;
&lt;input type=&quot;checkbox&quot; id=&quot;opt-in&quot;&gt;</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/95429222-6cd5-4664-9019-9478612a0b90/image.png" /></p>
<h3 id="checked-속성">#checked 속성</h3>
<ul>
<li>페이지가 처음 로드될 때 체크박스가 체크된 상태로 시작</li>
<li>페이지가 로그된 후 사용자가 체크박스를 체크하거나 체크 해제해도 속성은 변하지 않음.</li>
</ul>
<pre><code class="language-html">&lt;input type=&quot;checkbox&quot; checked&gt;</code></pre>
<h3 id="disabled-속성">#disabled 속성</h3>
<ul>
<li>체크박스를 비활성시킬 때 사용</li>
</ul>
<pre><code class="language-html">&lt;input type=&quot;checkbox&quot; disabled&gt;</code></pre>