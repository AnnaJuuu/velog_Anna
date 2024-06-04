<p>코틀린 문법을 공부하기 전에 풀었던 문제를 다시 가지고 와서 다시 풀기!</p>
<h3 id="두-수의-차곱합몫-구하기-동일">두 수의 차(곱/합/몫 구하기 동일)</h3>
<img src="https://velog.velcdn.com/images/a700hui/post/9234c79c-f627-4de1-9d55-ab6997b65303/image.png" width="80%" />

<pre><code class="language-kotlin">//첫 문제 풀이
class Solution 
{
    fun solution(num1: Int, num2: Int): Int 
    {
        var answer: Int = 0 
        return num1 - num2
    }
}

//재풀이
class Solution 
{
    fun solution(num1: Int, num2: Int): Int = num1 - num2
}</code></pre>
<p>첫 풀이는 다 return 따로 적고 연산을 했었는데, <a href="https://velog.io/@a700hui/%ED%95%A8%EC%88%98"><strong>함수</strong></a>에 return 생략한 표현식(간략화된 함수)이 생각나서 줄여봄</p>
<h3 id="각도기">각도기</h3>
<img src="https://velog.velcdn.com/images/a700hui/post/65d74ee6-12b8-40f1-9f4f-515d4785115a/image.png" width="80%" />

<pre><code class="language-kotlin">//첫 재풀이  !!!!에러!!!!
class Solution 
{
    fun solution(angle: Int): Int 
    {
        when(angle)
        {
            in 1.. 89 -&gt; {1}   //조건의 범위와 기본 사용이랑 헷갈림
            in 90 -&gt; {2}       
            in 91..179 -&gt;{3}
            in 180 -&gt; {4}      
        }
    }          //return 0 무슨 뜻인지 몰라서 깜빡함 
}


//Chet GPT한테 물어본 후 수정
class Solution 
{
    fun solution(angle: Int): Int 
    {
        when(angle)
        {
            in 1.. 89 -&gt; return 1
            90 -&gt; return 2   //in는 값의 특정 범위 내에 있는 확인할 때 사용
            in 91..179 -&gt; return 3
            180 -&gt; return 4  //단일 값은 in없이 사용!
        }
        return 0   //주어진 조건들 중 어느 것에도 해당하지 않을 때 반환된다. 
    }
}


//return when
class Solution 
{
    fun solution(angle: Int): Int 
    {
        return when(angle) 
        {
            in 1..89 -&gt; 1
            90 -&gt; 2
            in 91..179 -&gt; 3
            180 -&gt; 4
            else -&gt; 0  
        }
    }
}</code></pre>
<p><a href="https://velog.io/@a700hui/%EC%A1%B0%EA%B1%B4%EB%AC%B8%EA%B3%BC-%EB%B0%98%EB%B3%B5%EB%AC%B8"><strong>조건문과 반복문</strong></a></p>
<ol>
<li>in는 범위 내에서 사용</li>
<li>조건 이외에 상황은 0으로 리턴하기</li>
<li>when 안에 있는 값을 하나씩 리턴하기가 있고, when전체를 return하는 방법도 있다. </li>
<li>if문으로도 풀이 가능하다. <pre><code class="language-kotlin">class Solution 
{
 fun solution(angle: Int): Int 
 {
     if(angle &lt; 90) {answer = 1}
     else if(angle==90) {answer = 2}
     else if(angle&lt;180) {answer = 3}
     else if(angle==180) {answer = 4}
     return answer
 }
}</code></pre>
</li>
</ol>
<h3 id="느낀점">느낀점</h3>
<p>사전 캠프 때 알고리즘 코드카타를 8개만 풀고 멈추고 코틀린 문법을 공부 시작한게 잘한거 같다. 아무것도 모르는 상황에서 계속 문제를 풀려고 했으면 아마 지금 쯤 포기했을거 같다... 덕분에 프로그래밍의 공부법을 찾은거 같다. 나는 이론 먼저 공부하고 실습하는 체질이다!! 혼자서 문제 푸는 맛도 나고, 다른 풀이 법도 고민할 수 있어서 너무 좋음. </p>