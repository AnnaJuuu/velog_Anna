<h3 id="lv1-기본-계산기-클래스-만들기">lv1 기본 계산기 클래스 만들기</h3>
<p><code>Calculator 클래스 만들기</code>
더하기, 빼기, 나누기, 곱하기 기능을 가진 클래스를 작성합니다.
<code>클래스를 이용한 연산</code> 
이 클래스를 이용하여 몇 가지 연산을 수행하고 결과를 출력합니다.</p>
<h3 id="class">class</h3>
<p><strong><code>✍🏻 클래스 첫 시도</code></strong></p>
<pre><code class="language-kotlin">//에러 코드입니다!!!
class Calculator
{
    //AddOperation(더하기), SubstractOperation(빼기), 
    //MultiplyOperation(곱하기), DivideOperation(나누기)
    fun AddOperation (num1 : Double, num2 : Double) : Double = num1 + num2
    fun SubstractOperation (num1 : Double, num2 : Double) : Double = num1 - num2
    fun MultiplyOperation (num1 : Double, num2 : Double) : Double = num1 * num2
    fun DivideOperationn (num1 : Double, num2 : Double) : Double = num1 / num2

}</code></pre>
<p>대략적인 틀은 알겠지만 세부적인 문법은 안 보면 짤 수 없다.. 
<strong>위 코드의 문제점</strong> : 변수 num1과 num2를 지정하지 않았고, 초기화 하지도 않았다. 연산 변수도 만들지 않았다. </p>
<p><strong><code>✍🏻 클래스 수정</code></strong></p>
<pre><code class="language-kotlin">class Calculator
{
    var num1 :Double = 0.0
    var num2 : Double = 0.0
    var operator : String = &quot;&quot;

    //AddOperation(더하기), SubstractOperation(빼기),
    //MultiplyOperation(곱하기), DivideOperation(나누기)
    fun AddOperation (num1 : Double, num2 : Double) : Double = num1 + num2
    fun SubstractOperation (num1 : Double, num2 : Double) : Double = num1 - num2
    fun MultiplyOperation (num1 : Double, num2 : Double) : Double = num1 * num2
    fun DivideOperationn (num1 : Double, num2 : Double) : Double = num1 / num2

}</code></pre>
<h3 id="main">main</h3>
<p><strong><code>🤦🏻‍♀️ main 첫 시도</code></strong></p>
<pre><code class="language-kotlin">//에러 코드입니다!!!!
fun main()
{
//콘솔에 입력해야하니까 .readLine()를 사용했다
    println(&quot;첫번 째 숫자를 입력해 주세요.&quot;)
    var num1.readLine()!!.toDouble

    println(&quot;원하는 연산자를 입력해 주세요.&quot;)
    var operator.readLine()!!.toString

    println(&quot;두번 째 숫자를 입력해 주세요.&quot;)
    var num2.readLine()!!.toDouble
}</code></pre>
<h4 id="문제점">문제점</h4>
<p>readLine() 앞에 .이 아닌 =로 사용하거나, main함수 안에서 Class Calulator를 사용하려면 클래스의 객체를 생성해야 한다.
나는 이 두가지 방법으로 다 풀어볼 예정이다. </p>
<p><strong><code>✍🏻 1. main 수정(readLine() 수정)</code></strong></p>
<pre><code class="language-kotlin">fun main()
{
    println(&quot;첫번 째 숫자를 입력해 주세요.&quot;)
    var num1 :Double = readLine()!!.toDouble()

    println(&quot;원하는 연산자를 입력해 주세요.&quot;)
    var operator :String = readLine()!!.toString()

    println(&quot;두번 째 숫자를 입력해 주세요.&quot;)
    var num2 :Double = readLine()!!.toDouble()

    var result :Double = 0.0

        when(operator)
    {
        &quot;+&quot; -&gt; {result = Calculator().AddOperation(num1, num2)}
        &quot;-&quot; -&gt; {result = Calculator().SubstractOperation(num1, num2)}
        &quot;*&quot; -&gt; {result = Calculator().MultiplyOperation(num1, num2)}
        &quot;/&quot; -&gt; {result = Calculator().DivideOperationn(num1, num2)}
            else -&gt; {&quot;잘못된 연산자입니다.&quot;
            Double.NaN}
    }
    println(&quot;결과 : ${result}&quot;)
}</code></pre>
<p><strong><code>2. ✍🏻 main 수정 (클래스의 객체 생성)</code></strong></p>
<pre><code class="language-kotlin">fun main()
{
//클래스의 객체를 생성
    val calculator = Calculator()

    println(&quot;첫번 째 숫자를 입력해 주세요.&quot;)
    calculator.num1 = readLine()!!.toDouble()

    println(&quot;원하는 연산자를 입력해 주세요.&quot;)
    calculator.operator = readLine()!!.toString()

    println(&quot;두번 째 숫자를 입력해 주세요.&quot;)
    calculator.num2 = readLine()!!.toDouble()

    val result = when(calculator.operator)
    {
        &quot;+&quot; -&gt; calculator.AddOperation(calculator.num1, calculator.num2)
        &quot;-&quot; -&gt; calculator.SubstractOperation(calculator.num1, calculator.num2)
        &quot;/&quot; -&gt; calculator.MultiplyOperation(calculator.num1, calculator.num2)
        &quot;*&quot; -&gt; calculator.DivideOperationn(calculator.num1, calculator.num2)
            else -&gt; &quot;잘못된 연산자입니다.&quot;
    }
    println(&quot;결과 = ${result}&quot;)
}</code></pre>
<h3 id="결과">결과</h3>
<p><strong><code>✍🏻 출력 문제 없음</code></strong></p>
<pre><code class="language-kotlin">첫번 째 숫자를 입력해 주세요.
10
원하는 연산자를 입력해 주세요.
+
두번 째 숫자를 입력해 주세요.
10
결과 = 20.0</code></pre>
<p><strong>나의 이번달 목표</strong> : 문법 참고하지 않고 내 머리로 코드 짜는 것!!!</p>