<h3 id="짝수와-홀수">짝수와 홀수</h3>
<img src="https://velog.velcdn.com/images/a700hui/post/c026c1c9-95cf-4e1b-bbbd-f244b1f20671/image.png" width="80%" />

<p><strong><code>1차 시도!! 또 다시 대실패!!</code></strong></p>
<pre><code class="language-kotlin">class Solution 
{
    fun solution(num: Int): String 
    {
        var answer = &quot;&quot;
//필요한 것은 단순히 주어진 num이 짝수인지 홀수인지 판별하여 하나의 문자열을 반환하는 것이다.. 
//반복할 필요가 없다!!! 
        for (i in 0..num )
        {
//반복문 안에 있는 루프 안에서 return 문장을 사용하면 첫 번째 반복에서 함수가 종료된다.... 
//원하는 답이 안 나올 수도 있다...
            return when (i)
            {

//when 표현식에서 조건을 i % 2 == 0 -&gt; {...} 형태로 사용하면 안 된다.
                i % 2 == 0 -&gt; {&quot;Even&quot;}
                //굳이??? else 쓰면 되잖여??
                i % 2 != 0 -&gt; {&quot;Odd&quot;}
            }
        }
    }
}</code></pre>
<p><strong><code>2차 시도!! 대성공!!</code></strong></p>
<pre><code class="language-kotlin">class Solution 
{
    fun solution(num: Int): String 
    {
        var answer = &quot;&quot;

        //when 표현식의 결과인 &quot;Even&quot; 또는 &quot;Odd&quot; 문자열을 answer 변수에 추가한다. 
        //좀 다르게 말하면 기존의 answer 문자열에 새로운 문자열을 덧붙인다! 
        answer += when 
        {
            num % 2 == 0 -&gt; &quot;Even&quot;
            else -&gt; &quot;Odd&quot;
        }
        return answer
    }
}

//위 코드를 좀 더 간결하게 한번 표현해봤다!
class Solution 
{
    fun solution(num: Int): String 
    {
    //반복문이 없기 때문에 when문 자체를 반환한다. 
        return when {
            num % 2 == 0 -&gt; &quot;Even&quot; // num이 짝수인 경우
            else -&gt; &quot;Odd&quot;         // num이 홀수인 경우
        }
    }
}</code></pre>
<p>그 이외도 if문으로 풀어봤다. </p>
<pre><code class="language-kotlin">class Solution 
{
    fun solution(num: Int): String 
    {
        var answer = &quot;&quot;

        return if (num % 2 == 0) 
        {&quot;Even&quot;}
        else {&quot;Odd&quot;}
    }
}</code></pre>