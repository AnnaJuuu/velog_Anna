<blockquote>
<p>정답은 없다.
폴더 이름 : 한글 x, 띄어쓰기 x, 대문자 x
계정 이름은 무조건 영어로</p>
</blockquote>
<hr />
<h3 id="html의-기본-구조">HTML의 기본 구조</h3>
<pre><code class="language-html">&lt;!DOCTYPE html&gt; &lt;!-- HTML 문서 타입을 선언하는 전문으로 HTML 요소 아님 --&gt;
&lt;html&gt; &lt;!-- HTML 문서의 시작 --&gt;
    &lt;head&gt;
        &lt;!-- 문서의 메타데이터 --&gt;
    &lt;/head&gt;
    &lt;body&gt;
        &lt;!-- 문서의 내용 --&gt;
    &lt;/body&gt;
&lt;/html&gt; &lt;!-- HTML 문서의 끝 --&gt;</code></pre>
<pre><code class="language-html">&lt;html&gt;
 &lt;head&gt;&lt;/head&gt;
 &lt;body&gt;
  &lt;h1&gt;나의 첫 HTML! 😎&lt;/h1&gt;
 &lt;/body&gt;
&lt;/html&gt;</code></pre>
<img src="https://velog.velcdn.com/images/a700hui/post/0ec4853b-4966-4e14-a04e-1af44a9d5f1d/image.png" width="30%" /> 

<p><code>&lt;p&gt;</code> 여는태그(Opening tag) : 요소의 이름과 열고 닫는 꺽쇠로 구성된다.
<code>&lt;/p&gt;</code> 닫는태그(Closing tag) : 요소의 이름 앞에 슬래시&quot;/&quot;가 붙는다.
<code>나의 첫 HTML! 😎</code> 내용(Content) : 요소의 내용이며, 단순한 텍스트를 의미한다.</p>
<hr />
<h3 id="주석-commandctrl--">주석 command(ctrl) + /</h3>
<pre><code class="language-html">&lt;!DOCTYPE html&gt;
&lt;html lang=&quot;en&quot;&gt;
&lt;head&gt;
 &lt;meta charset=&quot;UTF-8&quot;&gt;
 &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1.0&quot;&gt;
 &lt;title&gt;Document&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
 **&lt;!-- 주석을 사용하는 목적 --&gt;**
 **&lt;!-- 
 1. 아래 설명들을 붙여넣기 위한 목적
 2. 기능들을 설명하기 위한 목적 
 3. 그 이외 ... 
 --&gt;**
&lt;/body&gt;
&lt;/html&gt;</code></pre>
<hr />
<h3 id="태그">태그</h3>
<h4 id="string-b-글씨-굵게"><code>&lt;string&gt;</code>, <code>&lt;b&gt;</code> 글씨 굵게</h4>
<ul>
<li>두 태그의 표현은 동일하지만 사용 용도가 다르다.</li>
<li><code>&lt;b&gt;</code> 단순히 텍스트를 진하게 표시하는 역할</li>
<li><code>&lt;strong&gt;</code> 강조 뿐만 아니라 실제 페이지 내에서 중요한 부분을 브라우저에게 알려주는 역할을 한다.
브라우저에서 웹 접근성으로 인식되며, 스크린 리더로 페이지를 읽었을 때 거센 억양으로 음을 낼 수 있도록 강조한다.</li>
</ul>
<h4 id="em-i-글씨-기울이기"><code>&lt;em&gt;</code>, <code>&lt;i&gt;</code> 글씨 기울이기</h4>
<ul>
<li><code>&lt;i&gt;</code> 단순히 화면의 텍스트를 이태릭체로 표현</li>
<li><code>&lt;em&gt;</code> 그 내용이 중요하다는 의미도 함께 포함해준다.</li>
</ul>
<h4 id="mark-하이라이팅"><code>&lt;mark&gt;</code> 하이라이팅</h4>
<h4 id="del-delete"><code>&lt;del&gt;</code> delete</h4>
<ul>
<li>텍스트 중앙에 가로 줄을 그어서 텍스트를 지운 것과 같은 효과</li>
</ul>
<h4 id="ins-insert"><code>&lt;ins&gt;</code> insert</h4>
<ul>
<li>텍스트 밑에 선을 추가하여 텍스트 강조 효과</li>
</ul>
<h4 id="sup-sub-태그"><code>&lt;sup&gt;</code>, <code>&lt;sub&gt;</code> 태그</h4>
<ul>
<li>각주 번호(footnote numbers)로 사용</li>
<li>변수 참자로 사용</li>
<li>화학식에 사용
<a href="https://codingeverybody.kr/html-sub-%ed%83%9c%ea%b7%b8-%ec%98%ac%eb%b0%94%eb%a5%b8-%ec%9d%b4%ed%95%b4%ec%99%80-%ec%82%ac%ec%9a%a9-%eb%b0%a9%eb%b2%95/">HTML sub 태그 – 올바른 이해와 사용 방법</a></li>
</ul>
<h4 id="br--줄바꿈"><code>&lt;br /&gt;</code> 줄바꿈</h4>
<h4 id="p-문단"><code>&lt;p&gt;</code> 문단</h4>
<h4 id="q-인용-부호"><code>&lt;q&gt;</code> “인용 부호”</h4>
<pre><code class="language-html">  &lt;body&gt;
    &lt;p&gt;
      &lt;strong&gt;글씨를 굵게 만들어 주는 strong테그!&lt;/strong&gt; &lt;br /&gt;
      &lt;b&gt;글씨를 굵게 만들어 b테그!&lt;/b&gt;
    &lt;/p&gt;

    &lt;p&gt;
      &lt;em&gt;글씨를 기울이기&lt;/em&gt; &lt;br /&gt;
      &lt;i&gt;글씨를 기울이기&lt;/i&gt;
    &lt;/p&gt;

    &lt;h2&gt;&lt;sup&gt;제목&lt;/sup&gt; 입술의 말&lt;/h2&gt;

    &lt;h3&gt;최대호&lt;sub&gt;지음&lt;/sub&gt;&lt;/h3&gt;

    &lt;p&gt;
      &lt;q&gt;뭐해요?&lt;/q&gt;라는 말은 &lt;br /&gt;
      &amp;quot;뭐해요?&amp;quot;라는 말은 &lt;br /&gt;
    &lt;/p&gt;

    &lt;p&gt;
      &lt;ins&gt;걱정한다는 뜻.&lt;/ins&gt; &lt;br /&gt;
      &lt;del&gt;잘자라는 뜻&lt;/del&gt;
    &lt;/p&gt;

    &lt;mark&gt;전 세계 공통의 Language1&lt;/mark&gt;
    &lt;mark&gt;전 세계 공통의 Language2&lt;/mark&gt;

    &lt;p&gt;
      &lt;mark&gt;전 세계 공통의 Language3&lt;/mark&gt;
    &lt;/p&gt;
  &lt;/body&gt;</code></pre>
<img src="https://velog.velcdn.com/images/a700hui/post/0076c748-3f4d-4d8f-b43b-c03fc151bd71/image.png" width="50%" /> 


<hr />
<h3 id="특수-코드">특수 코드</h3>
<table>
<thead>
<tr>
<th>코드 값</th>
<th>표현</th>
</tr>
</thead>
<tbody><tr>
<td><code>&amp;lt;</code></td>
<td>&lt;</td>
</tr>
<tr>
<td><code>&amp;gt;</code></td>
<td>&gt;</td>
</tr>
<tr>
<td><code>&amp;amp;</code></td>
<td>&amp;</td>
</tr>
<tr>
<td><code>&amp;quot;</code></td>
<td>“</td>
</tr>
<tr>
<td><code>&amp;nbsp;</code></td>
<td>공백</td>
</tr>
</tbody></table>
<pre><code class="language-html">  &lt;body&gt;
    &lt;h3&gt;&lt;mark&gt;&amp;lt;celebrity&amp;gt;&lt;/mark&gt;&lt;/h3&gt;
    &lt;p&gt;
      &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;
      &lt;ins&gt;아이유&lt;/ins&gt;&lt;sub&gt;작사&lt;/sub&gt;
    &lt;/p&gt;

    &lt;strong&gt;
      &lt;em&gt;
        &lt;p&gt;
          발자국마다 이어진 별자리 &lt;br /&gt;
          그 서투른 걸음이 새겨놓은 밑그림
        &lt;/p&gt;

        &lt;p&gt;
          오롯이 너를 만나러 가는 길 &lt;br /&gt;
          그리로 가면 돼 점선을 따라
        &lt;/p&gt;

        &lt;p&gt;
          잊지마 이 오랜 겨울 사이 &lt;br /&gt;
          언 틈으로 피울 꽃 하나
        &lt;/p&gt;

        &lt;p&gt;
          보이니 하루 뒤 봄이 얼마나 &lt;br /&gt;
          아름다울지 말야.
        &lt;/p&gt;

        &lt;p&gt;&amp;quot;You are my &amp;amp;celebrity&amp;quot;&lt;/p&gt;
      &lt;/em&gt;
    &lt;/strong&gt;
  &lt;/body&gt;</code></pre>
<img src="https://velog.velcdn.com/images/a700hui/post/c35c9dc2-92d9-4808-849f-d99b47929501/image.png" width="40%" />