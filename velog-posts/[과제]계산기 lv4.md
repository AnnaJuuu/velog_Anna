<h3 id="lv4-추상화-적용하기">Lv4: 추상화 적용하기</h3>
<p><code>목표</code>
AddOperation, SubtractOperation, MultiplyOperation, DivideOperation 연산 클래스들을 AbstractOperation라는 추상 클래스로 만들어 사용하고, Calculator 클래스의 내부 코드를 변경한다.</p>
<p><code>설명</code>
AbstractOperation이라는 추상 클래스를 만든다.
개별 연산 클래스들이 이 추상 클래스를 상속받도록 한다.
Calculator 클래스는 이 추상 클래스를 사용하여 연산을 수행한다.</p>
<p><code>개선점</code>
코드의 결합도를 낮추고, 의존성역전원칙(Dependency Inversion Principle)을 적용하여 코드의 유연성을 높인다. 추상 클래스에 의존함으로써, 새로운 연산 클래스를 쉽게 추가할 수 있다.</p>
<p><code>class AbstractOperation</code></p>
<pre><code class="language-kotlin">abstract class AbstractOperation
{
    abstract fun operate(num1 : Double, num2 : Double) : Double
}
</code></pre>
<p><code>class AddOperation 하위 클래스</code></p>
<pre><code class="language-kotlin">class AddOperation : AbstractOperation()
{
    override fun operate(num1: Double, num2: Double): Double
    {
        return num1 + num2
    }
}</code></pre>
<p><code>class Calculator_lv4, main</code></p>
<pre><code class="language-kotlin">class Calculator_lv4
{
    fun operation(input : Int, num1 : Double, num2 : Double) : Double = when(input)
    {
        1 -&gt; AddOperation().operate(num1, num2)
        2 -&gt; SubtractOperation().operate(num1, num2)
        3 -&gt; MultiplyOperation().operate(num1, num2)
        4 -&gt; DivideOperation().operate(num1, num2)
        else -&gt; 0.0
    }
}

fun main()
{
    val calculator = Calculator_lv4()
    while(true)
    {
        println(&quot;아래 메뉴에서 선택해주세요.&quot;)
        println(&quot;[1] 더하기 연산 [2] 빼기 연산 [3] 곱하기 연산 [4] 나누기 연산 &quot;)
        println(&quot;주의 : -1입력시 계산기 바로 종료됩니다.&quot;)

        val input = readLine()!!.toInt()
        if (input == -1)
        {
            println(&quot;계산기 종료하겠습니다.&quot;)
            break
        } else if (input !in 1..4)
        {
            println(&quot;잘못된 선택입니다, 다시 입력해주세요\n&quot;)
            continue
        }

        println(&quot;첫번 째 숫자를 입력해주세요.&quot;)
        val num1 = readLine()!!.toDouble()
        if (num1 == -1.0)
        {
            println(&quot;계산기 종료하겠습니다.&quot;)
            break
        }

        println(&quot;두번 째 숫자를 입력해주세요.&quot;)
        val num2 = readLine()!!.toDouble()
        if (num2 == -1.0)
        {
            println(&quot;계산기 종료하겠습니다.&quot;)
            break
        }
        val result = calculator.operation(input, num1, num2)
        println(&quot;결과 : ${result}\n&quot;)
    }
}</code></pre>
<h3 id="조건에-충족한지">조건에 충족한지?</h3>
<p>추상화된 연산 클래스들 사용: 각 연산 클래스들이 AbstractOperation 추상 클래스를 상속받아 구현되었습니다.
의존성 역전 원칙 적용: Calculator_lv4 클래스에서 직접적으로 각 연산 클래스의 인스턴스를 생성하는 것이 아니라, AbstractOperation을 상속받은 구체적인 연산 클래스의 인스턴스를 사용하고 있습니다. 이것은 의존성 역전 원칙을 따르고 있습니다.
유연성과 확장성: 새로운 연산을 추가하기 위해서는 간단히 AbstractOperation을 상속받아 새로운 연산을 구현하면 됩니다.
코드의 간결성: 코드는 각 연산 클래스의 operate 메서드를 호출하여 간단하고 명확하게 작성되어 있습니다.
입력 유효성 검사: 입력값에 대한 유효성 검사가 수행되어 사용자가 잘못된 선택을 할 경우에 메시지가 출력됩니다.</p>