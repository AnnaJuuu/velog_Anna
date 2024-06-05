<h3 id="짝수의-합">짝수의 합</h3>
<img src="https://velog.velcdn.com/images/a700hui/post/2f31a44a-cdb0-4316-b229-2c987c9f3018/image.png" width="80%" />

<h4 id="문제-풀이">문제 풀이</h4>
<pre><code class="language-kotlin">// 시도1 대실패!!!!!!! 
class Solution 
{
    fun solution(n: Int): Int 
    {
        var answer : Int = 0
        // 반복문 까먹음
        return if (n % 2 == 0)   // if 앞에 return 사용 
        {
            answer += n
        } else 0
    }
}

//시도2 대성공!!!!!!
class Solution 
{
    fun solution(n: Int): Int 
    {
        var answer = 0
        for (i in 1..n)
        {
            if (i % 2 == 0)
            {
                answer += i
            } else 0
        }
        return answer
    }
}
</code></pre>
<p><strong><code>for (i in 1..n)</code></strong>
n를 반복 가능한 무언가로 바꾼다. <code>1..n</code> 1부터 n까지 반복한다. </p>
<p><strong><code>return 와 if</code></strong>
<code>return</code>은 함수의 실행을 즉시 종료하고 값을 반환한다. 따라서 <code>return</code>이 <code>if</code> 문 앞에 오면, 조건에 따라 반환 여부를 결정하는 것이 아니라 <strong>즉시 반환하게 되어 루프의 실행이 중단</strong>된다. </p>
<pre><code class="language-kotlin">for (i in 1..n) 
{
    if (i % 2 == 0) 
    {
        return i  // 이 경우 첫 번째 짝수를 만나면 함수가 종료되고 값을 반환합니다.
    }
}
//만약 이 코드를 원하지 않으면 return문을 루프 밖으로 빼야한다.
for (i in 1..n) 
{
    if (i % 2 == 0)
}
return i </code></pre>
<p><strong><code>return와 when</code></strong>
<code>if</code>와 달리 <code>when</code>는 구문 자체가 <strong>결과를 반환하는 표현식</strong>으로 사용될 수 있다. 
아래 코드처럼, <code>when</code> 구문이 <code>angle</code>를 평가하고 해당하는 조건에 맞는 값을 반환한다. when블록이 끝난 후에 최종적으로 반환된 값을 <code>return</code>이 반환하게 된다. </p>
<pre><code class="language-kotlin">return when(angle) 
{
    in 1..89 -&gt; 1
    90 -&gt; 2
    in 91..179 -&gt; 3
    180 -&gt; 4
    else -&gt; 0  
}</code></pre>