<h3 id="데이터-클래스-data-class">데이터 클래스 (data class)</h3>
<p>데이터 저장을 주 목적</p>
<p><strong>자동생성되는 매서드</strong>
<code>hashCode()</code> 객체를 구분하기 위한 고유값을 리턴해줘
<code>equals()</code> 동일한 객체인지 비교해서 true 또는 false를 리턴해줘
<code>copy()</code> 현재 객체의 모든 정보를 복사해서 새로운 객체를 리턴해줘
<code>toString()</code> 현재 객체의 모든 정보(프로퍼티)를 예쁘게 출력해줘
<code>getXXX()/setXXX(매개변수)</code> 변수의 값을 리턴하거나 설정해줘</p>
<hr />
<h3 id="데이터-클래스-선언하기">데이터 클래스 선언하기</h3>
<p><strong>data 키워드 사용, 아래 조건을 만족해야 한다.</strong> </p>
<ol>
<li>주 생성자는 최소한 하나의 매개변수를 가져야한다.</li>
<li>주 생성자의 모든 매개변수는 val, var로 지정된 프로퍼티여야 한다.</li>
<li>데이터 클래스는 abstract, open, sealed, inner 키워드를 사용할 수 없다.</li>
</ol>
<h3 id="👾-예제">👾 예제</h3>
<pre><code class="language-kotlin">//여기서 var 키워드를 사용하여 이 프로퍼티들이 읽기-쓰기 가능하도록 한다.
data class Customer(var name : String, var email : String) 
{
    var job : String = &quot;Unknown&quot;
    //보조 생성자
    constructor(name : String, email : String, _job : String) : this(name, email) 
    {
        job = _job
    }

    init //필요한 부생성자는 init블록은 사용이 가능
    {
        // 객체가 생성될 때 실행할 로직
    }
}
</code></pre>
<p><strong><code>주 생성자</code></strong>
name과 email 두 개의 프로퍼티를 받았다.</p>
<p><strong><code>추가 프로퍼티</code></strong>
job이라는 추가 프로퍼티, 초기값은 &quot;Unknown&quot;으로 설정</p>
<p><strong><code>보조 생성자</code></strong>
보조 생성자는 다른 방식으로 객체를 초기화할 수 있도록 한다. 
_job이라는 추가 인자를 받아 job 프로퍼티를 설정한다.</p>
<p><strong><code>this 호출</code></strong> 
보조 생성자는 반드시 주 생성자를 호출해야 한다. 여기서는 this(name, email)를 사용하여 주 생성자를 호출하고 있다.</p>
<p><strong><code>init</code></strong>
초기화 블록은 객체가 생성될 때 실행된다. 여기서는 빈 블록으로 되어 있지만, 객체 초기화 시 실행할 추가 코드를 작성할 수 있다.</p>
<hr />
<h3 id="실드-클래스-sealed-class">실드 클래스 (sealed class)</h3>
<ul>
<li>상속을 통해 클래스 계층 구조를 만들 때, 가능한 하위 클래스들을 제한하고 싶을 때 사용</li>
<li>컴파일 시점에 생성할 수 있는 자식을 알 수 있기때문에 효율적으로 다형성을 구현한다 </li>
</ul>
<h4 id="특징">특징</h4>
<p><code>제한된 상속</code> sealed 클래스의 모든 하위 클래스는 반드시 같은 파일 내에 정의되어야 한다. 
<code>추상 클래스</code>  sealed 클래스는 인스턴스화할 수 없으며, 기본적으로 추상 클래스다
<code>when 구문과의 통합</code> when 구문에서 모든 하위 클래스를 처리하지 않으면 컴파일러가 경고를 주어, 모든 경우를 처리하도록 강제할 수 있다. </p>
<pre><code class="language-kotlin">sealed class 부모클래스 
{
    class 자식클래스1 : 부모클래스생성자
    class 자식클래스2 : 부모클래스생성자
}</code></pre>
<hr />
<h3 id="👾-예제-1">👾 예제</h3>
<pre><code class="language-kotlin">sealed class NetworkResult
{
    data class Success(val data: String) : NetworkResult()
    data class Error(val exception: Exception) : NetworkResult()
    object Loading : NetworkResult()
}</code></pre>
<p><code>NetworkResult</code>
seales class로, 상속받는 클래스들이 제한된다. 
상속된 클래스는 동일한 파일 내에 선언되어야 한다.</p>
<p><code>data class Success</code>
성공을 나타내는 데이터 클래스를 정의하고, 
<code>val data: String</code>
매개변수로 문자열 데이터를 받도록 만들고, 
<code>: NetworkResult()</code>
NetworkResult의 하위 클래스로 사용하여 인스턴스화할 수 있다.
<code>val exception: Exception</code>
해당 클래스에 예외를 전달하여 예외를 포함시킬 수 있다.</p>
<p><code>Loading</code>은 <code>NetworkResult</code>를 상속받는 객체로, 네트워크 요청이 진행 중임을 나타낸다. 객체로 정의된 이유는 상태를 나타내기 위한 고유한 인스턴스를 가지기 위함이다. </p>
<pre><code class="language-kotlin">fun handleResult(result: NetworkResult)
{
    when (result)
    {
        is NetworkResult.Success -&gt; println(&quot;Success: ${result.data}&quot;)
        is NetworkResult.Error -&gt; println(&quot;Error: ${result.exception.message}&quot;)
        NetworkResult.Loading -&gt; println(&quot;Loading...&quot;)
    }
}</code></pre>
<p><code>handleResult</code>함수 선언 후 <code>result</code> 인자를 <code>NetworkResult</code> 타입으로 정의
<code>result</code> 변수에는 <code>NetworkResult</code> 클래스 또는 그 하위 클래스의 객체가 전달될 것이다. 
<code>result</code>변수의 타입이 <code>when</code>구문중 하나인 경우, 해당 메시지와 데이터를 출력</p>
<pre><code class="language-kotlin">fun main()
{
    val success = NetworkResult.Success(&quot;Data loaded successfully&quot;)
    val error = NetworkResult.Error(Exception(&quot;Network error&quot;))
    val loading = NetworkResult.Loading

    handleResult(success)  // Success: Data loaded successfully
    handleResult(error)    // Error: Network error
    handleResult(loading)  // Loading...
}</code></pre>
<p>val과 var로 변수를 선언하는 것은 새로운 객체를 생성하는 것이 아니라, 해당 변수를 위한 저장소를 확보하는 것이다. 하지만 <strong>클래스의 인스턴스를 참조하기 위해 변수를 만드는 것은 실제로 객체를 생성하는 것과 같다</strong>. 변수는 해당 클래스의 인스턴스를 참조하는데 사용되므로, 객체를 생성하는 것과 동일한 결과를 가져온다. </p>
<p><code>val success</code>, <code>val error</code>, <code>val loading</code>은 각각 
<code>NetworkResult.Success</code>, <code>NetworkResult.Error</code>, <code>NetworkResult.Loading</code>의 인스턴스를 참조하는 변수다. </p>
<p>생성한 객체들을 <code>handleResult</code> 함수에 전달하여 각각의 상태에 따른 메시지를 출력한다. </p>