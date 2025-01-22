<p><strong><code>li</code></strong> 리스트</p>
<h3 id="ol-순서가-있는-리스트-ordered-list">ol 순서가 있는 리스트 (<strong>ordered list)</strong></h3>
<pre><code class="language-html">&lt;ol&gt;
    &lt;li&gt;리스트 1&lt;/li&gt;
    &lt;li&gt;리스트 2&lt;/li&gt;
    &lt;li&gt;리스트 3&lt;/li&gt;
    &lt;li&gt;리스트 4&lt;/li&gt;
    &lt;li&gt;리스트 5&lt;/li&gt;
    &lt;li&gt;
        리스트 6
        &lt;ul&gt;
            &lt;li&gt;순서가 없는 하위 리스트&lt;/li&gt;
        &lt;/ul&gt;
    &lt;/li&gt;
&lt;/ol&gt;</code></pre>
<img src="https://velog.velcdn.com/images/a700hui/post/4ce74206-2ae0-4641-81e6-a93038d52c5f/image.png" width="40%" /> 


<h3 id="ul-순서가-없는-리스트unordered-list"><strong>ul 순서가 없는 리스트(unordered list)</strong></h3>
<pre><code class="language-html">&lt;ul&gt;
    &lt;li&gt;아이템 1&lt;/li&gt;
    &lt;li&gt;아이템 2&lt;/li&gt;
    &lt;li&gt;아이템 3&lt;/li&gt;
&lt;/ul&gt;</code></pre>
<img src="https://velog.velcdn.com/images/a700hui/post/6b2a0451-ca1d-440c-921b-eef426e399b5/image.png" width="20%" /> 


<h3 id="type-속성">type 속성</h3>
<p>type 속성의 값 : <strong><code>1</code>  <code>A</code>  <code>a</code>  <code>i</code>  <code>I</code></strong></p>
<p>속성을 사용하는 방법 : key = value</p>
<img src="https://velog.velcdn.com/images/a700hui/post/40a73fbd-91a5-40d6-8ed9-559accb0bade/image.png" width="30%" /> 


<pre><code class="language-html">&lt;body&gt;
&lt;h1&gt;1. 순서가 있는 리스트&lt;/h1&gt;
 &lt;p&gt;오늘 야식 리스트&lt;/p&gt;
 &lt;ol&gt;
  &lt;li&gt;곱창&lt;/li&gt;
  &lt;li&gt;닭발&lt;/li&gt;
  &lt;li&gt;요아정&lt;/li&gt;
 &lt;/ol&gt;

&lt;h1&gt;2. 순서가 없는 리스트&lt;/h1&gt;  
&lt;p&gt;버킷리스트&lt;/p&gt;
  &lt;ul&gt;
   &lt;li&gt;다이빙 자격증 따기&lt;/li&gt;
   &lt;li&gt;유럽여행&lt;/li&gt;
   &lt;li&gt;부자되기&lt;/li&gt;
  &lt;/ul&gt;

 &lt;h1&gt;실습&lt;/h1&gt;
  &lt;ol type=&quot;A&quot;&gt;
   &lt;li&gt;
    제1조(서비스 이용시간)
    &lt;ul&gt;
     &lt;li&gt;
      서비스 이용시간은 당 사이트의 업무상 또는 기술상 특별한 지장이 없는 한 연중무휴, 1일 24시간을 원칙으로 합니다.
     &lt;/li&gt;
     &lt;li&gt;
      제1항의 이용시간은 정기점검 등의 필요로 인하여 당 사이트가 정한 날 또는 시간은 예외로 합니다.
     &lt;/li&gt;
    &lt;/ul&gt;
   &lt;/li&gt;

   &lt;li&gt;
    제2조(개인정보의 처리 및 보유기간)
   &lt;p&gt;
    &quot;정부24&quot;에서 처리하는 개인정보는 수집·이용 목적으로 명시한 범위 내에서 처리하며, 개인정보보호법 및 관련 법령에서 정하는 보유기간을 준용하여 이행하고 있습니다.
   &lt;/p&gt;
    &lt;ol&gt;
     &lt;li&gt;
      정부24 회원정보
      &lt;ul&gt;
       &lt;li&gt;
        수집근거 : 정보주체의 동의, 전자정부법 시행령 제90조
       &lt;/li&gt;
       &lt;li&gt;
        보유기간 : 탈퇴 후 5일까지
       &lt;/li&gt;
      &lt;/ul&gt;
     &lt;/li&gt;
     &lt;li&gt;
      전자민원 신청이력(상담이력 포함)
      &lt;ul&gt;
       &lt;li&gt;
        수집근거 : 정보주체의 동의, 전자정부법 시행령 제90조
       &lt;/li&gt;
       &lt;li&gt;
        보유기간 : 3년
       &lt;/li&gt;
      &lt;/ul&gt;
     &lt;/li&gt;
    &lt;/ol&gt;
   &lt;/li&gt;
  &lt;/ol&gt;
&lt;/body&gt;</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/dcb6b4a4-df43-46a2-9ec8-d64a71149de4/image.png" /></p>