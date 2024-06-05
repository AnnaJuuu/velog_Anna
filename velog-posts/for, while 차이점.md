<h3 id="for-루프">for 루프</h3>
<pre><code class="language-kotlin">for (i in 1..10)  //1..10 범위를 사용하여 i를 초기화하고 조건을 내부적으로 확인
{
    println(&quot;${i}번째: 내 이름은 참새&quot;)
}</code></pre>
<h3 id="while-루프">while 루프</h3>
<pre><code class="language-kotlin">var i = 0  //초기화

while (i &lt; 10)  //위에서 i를 0으로 초기화했기 때문에 0부터 시작
{
    println(&quot;${i}번째: 내 이름은 참새&quot;)
    i++  //증가가 명시적으로 루프 본문 내에서 수행
}</code></pre>
<h4 id="루프-범위">루프 범위</h4>
<p><code>for</code>  i는 1에서 10까지의 값을 가진다. 
<code>while</code> i는 0에서 9까지의 값을 가진다. </p>
<h4 id="초기화">초기화</h4>
<p><code>for</code> 초기화가 암시적으로 루프 구문에 의해 처리된다. 
<code>while</code> 초기화가 명시적으로 루프 외부에서 수행한다. </p>
<h4 id="증가">증가</h4>
<p><code>for</code> 증가가 암시적으로 루프 구문에 의해 처리된다. 
<code>while</code> 증가가 명시적으로 루프 본문 내에서 수행된다. </p>