<h3 id="속성이란">속성이란?</h3>
<ul>
<li>하나의 태를 여러 번 사용할 수 있으니, 다른 부분에서 그 태그를 구분할 때 구분점이 없어서, key와 value를 통해 재사용할 수 있게 만들어주는 것이 속성이다.</li>
</ul>
<h3 id="블록-요소-block-element">블록 요소 Block Element</h3>
<ul>
<li>사용 가능한 최대 너비를 가진다. 높이는 내부 컨텐츠 크기만큼 설정됨. 즉, <strong>한 줄을 모두 사용함.</strong><ul>
<li><code>{width: 100%; height: auto;}</code> 와 같은 css 속성을 default로 가진다고 생각하면 됨</li>
</ul>
</li>
<li><code>width</code>, <code>height</code>로 크기를 지정할 수 있음</li>
<li><code>padding</code>, <code>margin</code>으로 상하좌우 여백을 지정할 수 있음</li>
<li>여러개의 블록 요소들이 있을 때 <strong>수직</strong>으로 쌓임</li>
</ul>
<blockquote>
<p>p, h1~6, ul, ol, div, form, table, ... 등이 있음</p>
<p><code>div</code> 태그</p>
<ul>
<li>다른 HTML 요소들을 하나로 묶는 데 사용되는 대표적인 블록 요소이다.</li>
<li>주로 여러 요소들의 스타일을 한 번에 적용하기 위해 div태그를 사용한다.</li>
</ul>
</blockquote>
<h3 id="인라인-요소-inline-element">인라인 요소 Inline Element</h3>
<ul>
<li>너비와 높이를 내부 컨텐츠 크기만큼 설정됨. 즉, 안에 있는 <strong>내용 만큼의 영역을 차치</strong>함<ul>
<li><code>{width: auto; height: auto;}</code>와 같은 css 속성을 default로 가진다고 생각하면 됨</li>
</ul>
</li>
<li><code>padding</code>, <code>margin</code>으로 좌우에만 여백을 지정할 수 있음 (위, 아래는 안됨)</li>
<li>width, height 안됨</li>
<li>여러개의 인라인 요소가 있을 때 <strong>수평</strong>으로 쌓임</li>
</ul>
<blockquote>
<p>span, a, img, strong, em, ... 등</p>
</blockquote>
<h3 id="인라인-블록-요소-inline-block-element"><strong>인라인 블록 요소 Inline-Block Element</strong></h3>
<ul>
<li>인라인 요소처럼 너비와 높이가 <strong>내부 컨텐츠 크기만큼 설정 됨</strong></li>
<li>블록 요소처럼 <code>width</code>와 <code>height</code>로 너비와 높이를 설정할 수 있음</li>
<li>블록 요소처럼 <code>padding</code>과 <code>margin</code>으로 상하좌우 여백을 지정할 수 있음</li>
<li>인라인 요소처럼 여러개의 인라인블록 요소가 있을때, <strong>수평</strong>으로 쌓인다</li>
<li>인라인블록 요소를 생성하려면, css의 <code>{display: &quot;inline-block&quot;;}</code>으로 스타일을 적용해야 함</li>
</ul>
<blockquote>
<p>button, input, select, ...</p>
</blockquote>