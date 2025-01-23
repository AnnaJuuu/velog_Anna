<ul>
<li>사용자 인터페이스를 제공하는 컨트롤 요소들의 label(이름표)를 나타낸다.</li>
<li>이 태그는 컨트롤 요소들과 함께 사용하며, 가독성과 <strong>웹 접근성을 높이는 역할</strong>을 한다.</li>
</ul>
<hr />
<h3 id="lable-가능-요소">lable 가능 요소</h3>
<p><code>input</code> : type 속성의 값이 <code>hieend</code>, <code>button</code>, <code>reset</code>, <code>submit</code>이 아닌 경우</p>
<p><code>textarea</code> <code>select</code> <code>progress</code> <code>output</code></p>
<hr />
<h3 id="사용할-필요가-없는-요소">사용할 필요가 없는 요소</h3>
<p><code>button</code>, <code>&lt;input type=”button”&gt;</code>, <code>&lt;input type=”submit”&gt;</code>, <code>&lt;input type=”reset”&gt;</code></p>
<ul>
<li>텍스트가 자체적으로 이름표를 나타내는 역할을 하기 때문에 <code>&lt;label&gt;</code> 태그가 필요없음</li>
</ul>
<hr />
<h3 id="label과-컨트롤-요소의-연결"><code>&lt;label&gt;</code>과 컨트롤 요소의 연결</h3>
<pre><code class="language-html">&lt;!--
    # 매칭할 컨트롤 요소의 id 값인 &quot;user-checking&quot;을
    # label 태그의 for 속성의 값으로 지정했습니다.
--&gt;
&lt;label for=&quot;user-checking&quot;&gt;저를 클릭하세요.&lt;/label&gt;&lt;input type=&quot;checkbox&quot; id=&quot;user-checking&quot;&gt;</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/8fc81ec1-bdf1-4326-8aa8-49ea1990dcb3/image.png" /></p>
<p>이 방식 외에도, <code>&lt;label&gt;</code>태그와 연결하여 매칭할 컨트롤 요소의 <code>id</code> 값을 <code>&lt;label&gt;</code>태그의 <code>for</code> 속성의 값으로 지정하지 않고 다음과 같이 <code>&lt;label&gt;</code>태그와 매칭할 컨트롤 요소를 연결할 수도 있다.</p>
<pre><code class="language-html">&lt;label&gt;
    저를 클릭하세요.
    &lt;input type=&quot;checkbox&quot;&gt;
&lt;/label&gt;</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/a44c5a8e-cc0b-4838-93e2-0257c7053a20/image.png" /></p>
<hr />
<h3 id="label태그-안에-인터렉티브-요소-배치-금지"><label>태그 안에 인터렉티브 요소 배치 금지</h3>
<ul>
<li><code>&lt;label&gt;</code> 태그 안에 <code>&lt;a&gt;</code>나 <code>&lt;button&gt;</code>과 같은 인터렉티브 요소를 배치XX</li>
<li>사용자에게 <code>&lt;label&gt;</code>과 관련된 컨트롤 요소에 접근하는데 방해됨</li>
</ul>
<pre><code class="language-html">&lt;label&gt;
    &lt;input type=&quot;checkbox&quot; name=&quot;privacy&quot;&gt;
    개인정보처리방침에 동의합니다.
&lt;/label&gt;
&lt;p&gt;&lt;a href=&quot;privacy.html&quot;&gt;개인정보처리방침 보기&lt;/a&gt;&lt;/p&gt;</code></pre>