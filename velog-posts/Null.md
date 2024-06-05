<h3 id="기본-개념">기본 개념</h3>
<p><strong>1. 객체와 변수</strong>
컴퓨터 프로그램에서 객체는 현실 세계의 사물을 표현하는 것이라고 생각할 수 있다. 예를 들어, &quot;자동차&quot;라는 객체는 속성(색상, 속도)과 행동(가속, 감속)을 가질 수 있다. 
변수는 이러한 객체를 가리키는 이름표 같은 거다. 예를 들어, myCar라는 변수는 &quot;자동차&quot; 객체를 가리킬 수 있다. </p>
<p><strong>2. null</strong>
null은 &quot;아무것도 없다&quot;는 뜻이다. 즉, 변수가 어떤 객체도 가리키고 있지 않을 때 사용하는 특별한 값이다. 예를 들어, myCar = null은 myCar가 현재 어떤 자동차도 가리키고 있지 않다는 뜻이다.</p>
<hr />
<h3 id="npenullpointerexception">NPE(NullPointerException)</h3>
<p>NullPointerException은 프로그래밍할 때 아주 흔히 발생하는 오류 중 하나다. 이 오류는 프로그램이 <strong>null인 변수를 사용하려고 할 때 발생한다</strong>. 쉽게 말하면, 아무것도 가리키고 있지 않은 변수로 뭔가 하려고 할 때 생기는 문제다.</p>
<h3 id="kotlin에서의-npe">Kotlin에서의 NPE</h3>
<p>Kotlin은 null을 안전하게 다룰 수 있도록 설계되어 있다. 기본적으로 변수는 null을 가질 수 없고, <strong>null을 가질 수 있는 변수는 따로 표시</strong>해야 한다. 이를 통해 NPE를 방지할 수 있다.</p>
<hr />
<h3 id="null">Null</h3>
<p>Null 객체를 선언할때 변수 타입 옆에 ? 를 붙이면 Null 사용이 가능하도록 할당할 수 있다. </p>
<pre><code class="language-kotlin">var nullable: String? = null

//변수는 String 타입이므로 null을 가질 수 없음
var nonNullable1: String = &quot;Kotlin&quot; 

//변수가 String? 타입으로 선언, null허용
//초기값으로 &quot;Kotlin&quot;이 할당되어 있어 정상적으로 값을 출력
var nonNullable2: String? = &quot;Kotlin&quot;  

println(nullable) // null 출력
println(nonNullable) // Kotlin 출력</code></pre>
<hr />
<h3 id="non-null">non-null</h3>
<p>변수나 객체가 Null 값을 가질 수 없음을 보장하는 타입이다. 
Non-null 단언 연산자 <code>!!</code> Null이 아님을 단언할 때 사용한다. 만약 Null이면 NullPointerException을 발생시킨다. </p>
<pre><code class="language-kotlin">// nullableName이 Null이면 런타임 에러 발생
val length = nullableName!!.length </code></pre>
<hr />
<h3 id="safe-call">Safe-call</h3>
<p>Kotlin에서 <strong>null 안정성을 보장하기 위해 제공하는 도구</strong> 중 하나다. 이 연산자는 <code>?.</code>로 표시되며, 변수나 객체가 null일 수 있는 상황에서 안전하게 접근할 수 있도록 도와준다. 
<code>?.</code>를 사용하면 해당 객체가 <strong>null이 아닐 때만 뒤따르는 메서드나 속성을 호출</strong>하게 되고, 만약 null이라면 그냥 <strong>null</strong>을 반환해.</p>
<pre><code class="language-kotlin">fun main() 
{
    var nullable: String? = null

    // null이므로 safe call 연산자에 의해 null 출력
    println(nullable?.length)    // 출력 결과 null

    nullable = &quot;Kotlin&quot;

    // null이 아니므로 length 속성을 호출해 길이 출력
    println(nullable?.length)    // 출력 결과 6
}</code></pre>
<hr />
<h3 id="elvis-operator-엘비스-연산자">Elvis operator 엘비스 연산자</h3>
<p>Kotlin에서 제공하는 <strong>null 안정성을 보장하기 위한 도구</strong> 중 하나다. 엘비스 연산자는 <code>?:</code>로 표시되며, <strong>변수나 표현식이 null일 경우 대체값을 제공</strong>할 수 있다. </p>
<pre><code class="language-kotlin">fun main() 
{
    var nullable: String? = null

    // nullable이 null이므로 기본값 &quot;Default Value&quot;가 반환됨
    val result1 = nullable ?: &quot;Default Value&quot;
    println(result1)     // 출력 결과 &quot;Default Value&quot;

    nullable = &quot;Kotlin&quot;

    // nullable이 null이 아니므로 nullable의 값이 반환됨
    val result2 = nullable ?: &quot;Default Value&quot;
    println(result2)    // 출력 결과 &quot;Kotlin&quot;
}</code></pre>
<ol>
<li><p><strong>null일 경우 기본값 반환</strong>
엘비스 연산자는 왼쪽의 표현식이 null인지 확인하고, null이면 오른쪽의 값을 반환한다. 이를 통해 null을 안전하게 처리하고, 기본값을 제공할 수 있다. </p>
</li>
<li><p><strong>주로 사용되는 상황</strong>
변수에 null이 들어올 수 있는 경우 <strong>기본값을 제공</strong>하고 싶을 때
함수의 결과가 null일 때 <strong>대체값을 지정</strong>하고 싶을 때</p>
</li>
</ol>
<pre><code class="language-kotlin">// 이 함수는 user 객체를 인자로 받으며, 이 객체는 null일 수도 있다.
fun getUserName(user: User?): String 
{
    //user가 null이 아닌 경우 user.name을 반환
    //user가 null이라면 &quot;Unknown&quot;을 반환
    return user?.name ?: &quot;Unknown&quot;
}

data class User(val name: String)

fun main() 
{
    //user1은 User 객체로 &quot;Alice&quot;라는 이름을 가지고 있다.
    val user1: User? = User(&quot;Alice&quot;)
    //user2는 null이다. 
    val user2: User? = null

    println(getUserName(user1))   // 출력 결과 &quot;Alice&quot;
    println(getUserName(user2))   // 출력 결과 &quot;Unknown&quot;
}</code></pre>