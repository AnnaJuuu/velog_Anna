<h3 id="배열의-평균값">배열의 평균값</h3>
<img src="https://velog.velcdn.com/images/a700hui/post/531c0ac8-002f-4e87-933f-4100b03ae83a/image.png" width="80%" />

<p><strong>문제풀이</strong></p>
<pre><code class="language-kotlin">class Solution 
{
    fun solution(numbers: IntArray): Double 
    { 
        var answer = 0
        for (i in numbers) 
        {
            answer += i   
        }
        return answer.toDouble() / numbers.size 
    }
}</code></pre>
<p><code>(numbers: IntArray): Double</code>
numbers는 정수 배열타입이고, Double형으로 리턴</p>
<p><code>var answer = 0</code>
numbers 배열의 모든 요소의 합을 저장하기 위해 answer이라는 변수를 만들고 0으로 초기화한다. 초기화하지 않으면, 합산을 시작할 때 초기값이 없어서 계산이 제대로 이루어지지 않는다.</p>
<p><code>(i in numbers)</code> 
numbers 배열의 각 요소를 i 변수에 할당한다.</p>
<p><code>answer += i</code>
numbers 배열의 각 요소를 answer에 더한다.</p>
<p><code>return answer.toDouble() / numbers.size</code>
모든 요소의 합을 Double형으로 형변환하고 총 배열 수를 나눈 후 리턴한다. </p>
<h3 id="느낀점">느낀점</h3>
<p>문제를 풀다가 굳이 형변환 안하고 처음부터 DoubleArray로 타입 지정하면 더 편하지 않을까 싶은 생각으로 아래 코드를 작성했는데 에러가 뜨네 ^^.. ChatGPT한테 물어봤는데 분명히 한국어로 대답해줬는데 무슨 뜻인지 이해가 잘 안된다..ㅋㅋㅋ...ㅋ.ㅋ.ㅋ.ㅋ.. 그래서 후딱딱 튜터님께 가봤더니 애초에 문제가 IntArray로 정의한 상태였고, 형변환하라는 의도였기 때문에 에러가 났다고 한다!!! 
결론적으로 DoubleArray로 하면 오히려 더 편하다! </p>
<pre><code class="language-kotlin">class Solution 
{
    fun solution(numbers: DoubleArray): Double 
    {
        var answer : Double = 0.0
        for (i in numbers)
        {
            answer += i
        }
        return answer / numbers.size
    }
}</code></pre>
<blockquote>
<p><strong>에러 메세지</strong>
<code>error: type mismatch: inferred type is IntArray but DoubleArray was expected</code><dl>
이러한 오류가 발생하는 이유는 함수를 호출할 때 전달된 인수의 유형이 함수의 매개변수와 일치하지 않기 때문입니다.<dl>
예를 들어, 만약 Solution 클래스에 정의된 solution 함수를 호출할 때 IntArray를 전달한다면, 오류가 발생합니다. 왜냐하면 solution 함수의 매개변수가 DoubleArray이기 때문입니다.<dl>
따라서 오류를 해결하려면 함수를 호출할 때 올바른 유형의 인수를 전달해야 합니다. 만약 DoubleArray를 전달해야 한다면, 호출할 때도 DoubleArray를 전달해야 합니다.</p>
</blockquote>