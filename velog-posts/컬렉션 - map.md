<p><strong>객체의 이름</strong>을 통해 관리하는 컬렉션
{ } ←로 반환</p>
<p><strong><code>mapOf</code></strong> 불변형
<strong><code>mutableMapOf</code></strong> 가변형</p>
<h3 id="mapofk-v"><strong>mapOf(K, V)</strong></h3>
<p>컬렉션 인터페이스를 상속받지 않지만, 코틀린 컬렉션 타입이다. </p>
<p>K : key, V : value 쌍으로 저장한다. </p>
<p>key는 고유하지만 서로 다른 key가 동일한 value를 가리킬 수 있음 </p>
<p>두 개의 맵이 쌍이 순서와 상관없이 같은 쌍의 값을 포함하고 있으면 동일한 map이라고 판단됨. </p>
<blockquote>
<p>👀 <strong>제네릭</strong>
key : 이름으로 사용할 객체의 타입
value : 저장할 객테 타입 <br />
두 가지 있음. 추론 가능해서 생략 가능</p>
</blockquote>
<pre><code class="language-kotlin">mapOf(키 to 값, 키 to 값, ...)
mutableMapOf(키 to 값, 키 to 값, ...)</code></pre>
<pre><code class="language-kotlin">val map1 = mapOf(&quot;key1&quot; to 10, &quot;key2&quot; to 20, &quot;key3&quot; to 30)
val map2 = mapOf(1 to &quot;str1&quot;, 2 to &quot;str2&quot;, 3 to &quot;str3&quot;)
println(map1)  //{key1=10, key2=20, key3=30}
println(map2)  //{1=str1, 2=str2, 3=str3}</code></pre>
<hr />
<h3 id="mutablemapofk-v"><strong>mutableMapOf(K, V)</strong></h3>
<pre><code class="language-kotlin">val map1 = mutableMapOf(1 to &quot;str1&quot;, 2 to &quot;str2&quot;, 3 to &quot;str3&quot;)
val map2 = mutableMapOf(&quot;key1&quot; to 1, &quot;key2&quot; to &quot;String&quot;, &quot;key3&quot; to true)
println(map1) //{1=str1, 2=str2, 3=str3}
println(map2) //{key1=1, key2=String, key3=true}</code></pre>
<blockquote>
<p>👀 <strong>keys, value는 map에서만 사용 가능?</strong>
<code>keys</code>와 <code>values</code>는 <code>Map</code> 인터페이스에서 제공하는 프로퍼티로
<code>Map</code> 컬렉션에서만 사용 가능</p>
</blockquote>