<h3 id="lv3-연산-클래스를-개별적으로-만들기">Lv3: 연산 클래스를 개별적으로 만들기</h3>
<p><code>목표</code>
더하기, 빼기, 곱하기, 나누기 연산을 각각의 클래스(AddOperation, SubtractOperation, MultiplyOperation, DivideOperation)로 만든다.
이 클래스들과 Calculator 클래스 간의 관계를 설정한다. (나머지 연산자(%) 기능은 제외)</p>
<p><code>설명</code>
각 연산을 수행하는 개별 클래스를 만든다.
Calculator 클래스가 이 연산 클래스들을 사용하도록 변경한다.
Lv2와 비교하여 단일책임원칙(Single Responsibility Principle)을 적용한다.</p>
<p><code>개선점</code>
각 연산을 개별 클래스로 분리하여 책임을 분리한다. 이는 코드의 가독성 및 유지보수성을 높인다.</p>
<hr />
<pre><code class="language-kotlin">package com.example.calculatorC_lv3

//단일책임원칙 : 설계 원칙 중 하나, 클래스 또는 모듈이 하나의 기능 또는 책임만 가져야 한다는 것을 의미
class Calculator_lv3
{
    //private 사용하여 클래스 Calculator에서만 접근이 가능하고,
    //fun calculate에서는 호출해서 사용이 가능하지만 내부 데이터를 함부로 변경할 수 없다
    //아래 코드를 설명하자면, 각 클래스들의 인스턴스를 생성하여 각각의 연산을 수행할 준비를 하고 있다.
    private val addOperation = AddOperation()
    private val subtractOperation = SubtractOperation()
    private val multiplyOperation = MultiplyOperation()
    private val divideOperation = DivideOperation()

    //클래스 내에서 연산을 수행할 수 있도록 설정
    fun operation(input : Int, num1 : Double, num2 : Double) : Double = when(input)
        {
            1 -&gt; addOperation.Add(num1, num2)
            2 -&gt; subtractOperation.Substract(num1, num2)
            3 -&gt; multiplyOperation.Multiply(num1, num2)
            4 -&gt; divideOperation.Divide(num1, num2)
            else -&gt; {println(&quot;잘못된 입력입니다.&quot;)
            0.0}
        }
}

//클래스 내부에서 input, num1, num2를 초기화하지 않아도 된다.
//클래스 내부에서 연산 수행하고 리턴할 예정이라, main에서 값만 입력하면 된다.

fun main()
{

    val calculator = Calculator_lv3()
    while(true)
    {
        println(&quot;아래 메뉴에서 선택해주세요.&quot;)
        println(&quot;[1] 더하기 연산 [2] 빼기 연산 [3] 곱하기 연산 [4] 나누기 연산 &quot;)
        println(&quot;주의 : -1입력시 계산기 바로 종료됩니다.&quot;)

        val input = readLine()!!.toInt()

        if(input == -1)
        {
            println(&quot;계산기 종료합니다.&quot;)
            break
        }

        println(&quot;첫번 째 숫자를 입력하세요.&quot;)
        val num1 = readLine()!!.toDouble()
        if(num1 == -1.0)
        {
            println(&quot;계산기 종료합니다.&quot;)
            break
        }

        println(&quot;두번 째 숫자를 입력하세요.&quot;)
        val num2 = readLine()!!.toDouble()
        if(num2 == -1.0)
        {
            println(&quot;계산기 종료합니다.&quot;)
            break
        }

        val result = calculator.operation(input, num1 ,num2)
        println(&quot;결과 : ${result}\n&quot;)
    }
}
</code></pre>