<ul>
<li>CSS를 작성하다 보면 여러 요소에 <strong>같은 스타일</strong>을 적용해야 할 때가 많음.
→ 이럴 때 쉼표<code>,</code>를 사용하면 <strong>한 번에 여러 요소에 스타일을 적용</strong>할 수 있다. </li>
</ul>
<h3 id="예제-코드">예제 코드</h3>
<pre><code class="language-html">&lt;style&gt;
    /* 여러 요소에 동일한 스타일 적용 */
    h1, h2 {
      text-align: center;
    }

    /* 클래스 선택자를 그룹으로 묶어서 스타일 적용 */
    p.gray, strong.gray {
      color: gray;
    }

    p.red {
      color: red;
    }
  &lt;/style&gt;

...

&lt;body&gt;
  &lt;div&gt;
    &lt;h1&gt;안녕&lt;/h1&gt;
    &lt;h2&gt;여러 선택자에 공통된 스타일을 적용하는 방법&lt;/h2&gt;

    &lt;p class=&quot;gray&quot;&gt;
      쉼표(,)를 사용하면 여러 선택자를 한 번에 스타일링할 수 있다.
    &lt;/p&gt;

    &lt;p class=&quot;red&quot;&gt;
      예를 들어, h1과 h2를 **중앙 정렬**하려면  
      &lt;strong class=&quot;gray&quot;&gt;`h1, h2 { text-align: center; }`&lt;/strong&gt;  
      이렇게 한 줄로 작성하면 된다.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/body&gt;
</code></pre>
<blockquote>
<h3 id="✅--그룹-선택자-사용-시-장점">✅  그룹 선택자 사용 시 장점</h3>
<p><strong>코드가 짧아짐</strong> → 중복된 스타일을 제거할 수 있음</p>
<p><strong>유지보수 편리</strong> → 스타일을 한 곳에서 관리 가능</p>
<p><strong>가독성 향상</strong> → 여러 요소가 같은 스타일을 공유한다는 점이 명확해짐</p>
</blockquote>