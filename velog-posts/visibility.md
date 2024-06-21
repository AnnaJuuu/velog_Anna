<img src="https://velog.velcdn.com/images/a700hui/post/2b0996b0-b7ed-4749-8b25-9a8f71a77ea1/image.png" width="40%" />

<ul>
<li>visibility : 가시성</li>
<li>앱을 만들다보면 <strong>사용자와의 상호 작용을 통해</strong> 어떤 View 를 <strong>숨기거나, 표시</strong>하고 싶을 때 사용</li>
<li>모든 View 를 대상으로 사용할 수 있다.</li>
</ul>
<h3 id="visibility의-종류"><strong>visibility의 종류</strong></h3>
<p><strong><code>Visible</code></strong>  화면에 보이는 상태</p>
<p><strong><code>Invisible</code></strong>  화면에 보이진 않지만, 레이아웃에 자리를 차지하고 있는 상태</p>
<p><strong><code>Gone</code></strong>  완전히 숨겨진 상태</p>
<h3 id="사용법">사용법</h3>
<p><strong>xml에 사용법</strong></p>
<pre><code class="language-kotlin">android:visibility=&quot;속성&quot;</code></pre>
<p><strong>activity에 사용</strong></p>
<pre><code class="language-kotlin">val 변수명 : View타입 = findViewById(R.id.아이디)

변수명.setOnClickListener {
    변수명.visibility = View.visibility속성
}</code></pre>
<pre><code class="language-kotlin">fun showHide(view:View) 
{
    view.visibility = if (view.visibility == View.VISIBLE){
        View.INVISIBLE
    } else
    {
        View.VISIBLE
    }
}</code></pre>