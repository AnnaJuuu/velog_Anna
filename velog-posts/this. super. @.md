<h3 id="this-super">this. super.</h3>
<p>상위 클래스는 super 키워드로 현재 클래스는 this 키워드로 참조가능</p>
<table>
<thead>
<tr>
<th>super</th>
<th>상위 클래스</th>
<th>this</th>
<th>현재 클래스</th>
</tr>
</thead>
<tbody><tr>
<td>super.프로퍼티명</td>
<td>상위 클래스의 프로퍼티 참조</td>
<td>this.프로퍼티명</td>
<td>현재 클래스의 프로퍼티 참조</td>
</tr>
<tr>
<td>super.메서드명</td>
<td>상위 클래스의 메서드 참조</td>
<td>this.메서드명</td>
<td>현재 클래스의 메서드 참조</td>
</tr>
<tr>
<td>super()</td>
<td>상위 클래스의 생성자 참조</td>
<td>this()</td>
<td>현재 클래스의 생성자 참조</td>
</tr>
</tbody></table>
<h3 id="엣-기호의-이용">엣(@) 기호의 이용</h3>
<p>이너 클래스에서 바깥 클래스의 상위 클래스를 호출하려면 super 키워드와 함께 엣(@) 기호 옆에 바깥 클래스명을 작성해 호출</p>
<pre><code class="language-kotlin">class Outer 
{
    fun greetings() 
    {
        println(&quot;Hello from Outer class&quot;)
    }

    inner class Inner 
    {
        fun greetings() 
        {
            println(&quot;Hello from Inner class&quot;)

            // 외부 클래스의 greetings() 메서드 호출
            this@Outer.greetings() 
        }
    }
}

fun main() 
{
    val outer = Outer()
    val inner = outer.Inner()
    inner.greetings()
}</code></pre>
<p>위의 코드에서 <code>this@Outer.greetings()</code>는 이너 클래스의 greetings() 메서드가 아니라 외부 클래스인 <code>Outer 클래스의 greetings()</code> 메서드를 호출한다. </p>