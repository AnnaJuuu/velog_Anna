<h2 id="📖-문제">📖 문제</h2>
<p>함수 solution은 정수 <code>x</code>와 자연수 <code>n</code>을 입력 받아, <code>x</code>부터 시작해 <code>x</code>씩 증가하는 숫자를 <code>n</code>개 지니는 리스트를 리턴해야 합니다. 다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.</p>
<h2 id="📖-제한-조건">📖 제한 조건</h2>
<ul>
<li>x는 -10000000 이상, 10000000 이하인 정수입니다.</li>
<li>n은 1000 이하인 자연수입니다.</li>
</ul>
<hr />
<h2 id="👻-내-풀이">👻 내 풀이</h2>
<h3 id="👻-1차-코드">👻 1차 코드</h3>
<pre><code class="language-kotlin">class Solution 
{
    fun solution(x: Int, n: Int): List&lt;Long&gt;
    {
        var answer = mutableListOf&lt;Long&gt;() 

        for(i in 1..n)
        {
            answer.add(x.toLong() * i)
        }
        return answer
    }
}</code></pre>
<p><code>: List&lt;Long&gt;</code>
Long타입 리스트로 반환</p>
<p><code>var answer = mutableListOf&lt;Long&gt;()</code>
가변 리스트를 초기화, 이 리스트는 최종적으로 함수가 반환할 결과를 저장</p>
<p><code>answer.add(x.toLong() * i)</code>
x를 Long타입으로 변환한 후 i를 곱해서 answer 리스트에 추가한다. </p>
<h3 id="👻-다른-사람-풀이-해석">👻 다른 사람 풀이 해석</h3>
<pre><code class="language-kotlin">class Solution 
{
    fun solution(x: Int, n: Int): LongArray = LongArray(n) { x.toLong() * (it + 1) }
}
</code></pre>
<p><code>: LongArray</code>
LongArray로 형변환</p>
<p><code>LongArray(n)</code>
n인 LongArray 생성</p>
<p><code>{ x.toLong() * (it + 1) }</code>
x를 Long타입으로 변환, 
배열은 0부터 시작하기 때문에 +1해준다. 
여기서 it은 뭐지???  </p>
<hr />
<h2 id="📖-느낀점">📖 느낀점</h2>
<p>배열 공부 더 열심히 해야할 것! 개념은 알겠으나 활용은 못하고 있다..</p>