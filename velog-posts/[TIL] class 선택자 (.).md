<h2 id="class-선택자">class 선택자</h2>
<pre><code class="language-html"> &lt;style&gt;
  .blue-text {
   color: blue;
  }
  .red-text {
   color: red;
  }
  .green-text {
   color: green;
  }
 &lt;/style&gt;

...

&lt;body&gt;
 &lt;h1&gt;클래스 선택자&lt;/h1&gt;
 &lt;h2 class=&quot;blue-text&quot;&gt;특정 부분에 스타일 적용하기&lt;/h2&gt;
 &lt;p class=&quot;blue-text&quot;&gt;태그 선택자를 지정하면 그 태그가 사용된 모든 요소에 적용된다.&lt;/p&gt;
 &lt;p&gt;
  그런데 같은 태그라도 서로 다른 스타일을 사용하고 싶다면, 
  &lt;span class=&quot;red-text&quot;&gt;특정 그룹에만 스타일을 적용할 때 사용하는 것이 클래스 선택자이다. &lt;/span&gt;
  클래스 이름은 나중에 기억하기 쉬운 이름으로 지정하고, 여러 번 중복하여 이름을 설정할 수 있다. 
 &lt;/p&gt;
 &lt;p&gt;
  또한 &lt;span class=&quot;green-text&quot;&gt;class=&quot;green-text&quot;&lt;/span&gt;
  처럼 적용하여 어느 태그에서나 사용할 수 있다.
 &lt;/p&gt;
&lt;/body&gt;</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/38c8b494-5d1a-4cf8-bcb7-2f8067461bf9/image.png" /></p>
<pre><code class="language-html"> &lt;span id=&quot;z&quot; class=&quot;a b c d&quot;&gt;클래스와 아이디&lt;/span&gt;
 &lt;span id=&quot;a&quot;&gt;아이디는 중복이 불가능하지만, 클래스는 중복이 가능하다.&lt;/span&gt;</code></pre>
<p>클래스 이름이 a, b, c, d 총 4개 있다. </p>
<p>스타일을 아래처럼 주면 맨 아래 명령대로 바뀐다. </p>
<pre><code class="language-html">
  &lt;style&gt;
  .a {
   color: yellow;
  }

  .c {
   color: purple ;
  }

  .d{
   color: aqua;
  }
  &lt;/style&gt;</code></pre>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/e34fbda6-06fb-468f-99be-eaa10c5b1e8d/image.png" /></p>
<blockquote>
<p>아이디와 클래스 이름이 같아도 괜찮다.
아이디는 <code>#</code>, 클래스는 <code>.</code>을 사용하기 때문이다. </p>
</blockquote>