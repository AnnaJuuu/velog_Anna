<blockquote>
<p>베열을 크기가 정해지면 변경할 수 없지만, LIst는 추가, 삭제 등이 가능
<strong><code>listOf</code></strong> 불변형 리스트 생성
<strong><code>mutableListOf</code></strong> 가변형 리스트 생성  ()
<strong><code>emptyList</code></strong> 비어있는 불변형 리스트를 생성
<strong><code>listOfNotNull</code></strong> null을 제외한 나머지만으로 리스트를 생성</p>
</blockquote>
<p>👀 <strong>불변형&amp;가변형</strong></p>
<ul>
<li><p>불변형에 비해 메모리 많이 잡아 먹음, 속도 좀 느림</p>
</li>
<li><p>불변형 컬렉션 객체 사용 추천</p>
<ul>
<li>실제로 데이터 조작하는 작업을 할 때 가변형으로 새로 만들어서 작업한 후</li>
<li>불변형을 새로 만들어서 사용하는 것을 추천</li>
</ul>
</li>
</ul>
<hr />
<h3 id="listof">listOf</h3>
<pre><code class="language-kotlin">val list1 = listOf(10, 20, 30, 40, 50)
val list2 = listOf(&quot;str1&quot;, &quot;str2&quot;, &quot;str3&quot;, &quot;str4&quot;)

println(&quot;list1 : ${list1}&quot;)  //list1 : [10, 20, 30, 40, 50]
println(&quot;list2 : ${list2}&quot;)  //list2 : [str1, str2, str3, str4]</code></pre>
<blockquote>
<p>👀 <strong>제네릭</strong>
객체 생성할 때 데이터 지정해주지 않으면 
→ 제네릭 명시 필수 <strong><code>val lsit1 = listOf&lt;Int&gt;()</code></strong> <br />
데이터 지정해주면 제네릭 생략 가능 
→ 알아서 자료형 추론</p>
</blockquote>
<hr />
<h3 id="mutablelistof">mutableListOf</h3>
<pre><code class="language-kotlin">val list3 = mutableListOf&lt;Int&gt;()   
val list4 = mutableListOf(&quot;str1&quot;, &quot;str2&quot;, &quot;str3&quot;)
println(&quot;list3 : ${list3}&quot;)  //list3 : []
println(&quot;lsit4 : ${list4}&quot;)  //lsit4 : [str1, str2, str3]</code></pre>
<blockquote>
<p>👀 <strong>mutableListOf</strong>
나중에 값을 추가 가능 
-&gt; 아무것도 가지고 있지 않는 리스트를 만드는 경우도 굉장히 많음</p>
</blockquote>
<hr />
<h3 id="emptylist-listofnotnull"><strong>emptyList, listOfNotNull</strong></h3>
<pre><code class="language-kotlin">val list5 = emptyList&lt;String&gt;() //비어져 있는 불변형 -&gt; 무의미!!!

val list6 = listOfNotNull(10, 20, 30, null, 40, null)
println(&quot;list6 : ${list6}&quot;)  //list6 : [10, 20, 30, 40]</code></pre>
<blockquote>
<p>👀 null
그냥 리스트 → null포함
listOfNotNull → null빼고 리스트 만듬</p>
</blockquote>
<hr />
<h3 id="반복문">반복문</h3>
<pre><code class="language-kotlin">for (item in list1)
{
    println(&quot;list1 for : $item&quot;)
}

//list1 for : 10
//list1 for : 20
//list1 for : 30
//list1 for : 40
//list1 for : 50</code></pre>