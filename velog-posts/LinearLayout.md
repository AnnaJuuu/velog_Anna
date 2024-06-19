<p><strong>방향성</strong>을 가지고 view를 배치하는 layout이다. </p>
<p><strong>가로 혹은 세로 방향으로 배치</strong>할 수 있으며 <strong>한 칸에 하나의 View만 배치</strong>할 수 있다.</p>
<p>안드로이드에서 가장 많이 사용하는 layout으로 <strong>여러 LinearLayout을 조합</strong>하여 <strong>다양한 모양</strong>을 만들 수 있다. </p>
<h3 id="linearlayout-사용"><strong>LinearLayout 사용</strong></h3>
<p><strong><code>Palette</code></strong> 배치할 수 있는 요소들</p>
<img src="https://velog.velcdn.com/images/a700hui/post/cf028bfc-8762-462b-9569-42e7d4c337a5/image.png" width="30%" />

<p><strong><code>Component Tree</code></strong> 배치된 객층 구조</p>
<img src="https://velog.velcdn.com/images/a700hui/post/a822e26e-b24c-44c9-be17-b950924d4238/image.png" width="30%" />

<p>그냥 palette에서 사용해도 되지만, component tree에서 우클릭하고 선택 가능</p>
<img src="https://velog.velcdn.com/images/a700hui/post/c8eefcd8-a124-4c30-9087-043e58029c89/image.png" width="30%" />

<img src="https://velog.velcdn.com/images/a700hui/post/d17c2856-54e9-4c4f-92a6-47aee3218646/image.png" width="30%" />

<h3 id="linearlayout에-주요-속성"><strong>LinearLayout에 주요 속성</strong></h3>
<p><strong><code>orientation</code></strong> 배치 되는 방향성을 결정한다</p>
<img src="https://velog.velcdn.com/images/a700hui/post/14b2ec9f-5898-49ee-bffb-98b42a835f4e/image.png" width="40%" />


<blockquote>
<p>👀 <strong>orientation</strong></p>
<p><strong><code>vertical</code></strong> 세로 방향</p>
<p><strong><code>horizontal</code></strong> 가로 방향 (기본)</p>
</blockquote>
<h3 id="layout_weight"><strong>layout_weight</strong></h3>
<ul>
<li>LinearLayout 안에 배치되는 View들의 비율을 설정<ul>
<li>다 배치한 후에 <strong>남은 공간</strong>을 가져가기</li>
<li>위젯이 크기가 다른 상태에서 남은 공간을 서로 반 씩 가져가는 것이기 때문에</li>
<li>서로의 길이가 달라질 수 밖에 없다</li>
</ul>
</li>
</ul>
<blockquote>
<p>👀 <strong>layout_weight</strong></p>
<p><strong><code>android:weightSum = “5”</code></strong> 값을 상위(부모) 레이아웃에게 설정하고 하위 레리아웃에게 layout_weight를 3과 2를 각각 설정해주면 3:2비율로 레이아웃 길이가 설정 </p>
</blockquote>
<blockquote>
<p>👀 <strong>폰트, 사이즈</strong></p>
<p>File - Setting - Editor - Font &gt; 폰트 크기 </p>
<p>File - Setting - Appearance - use custom font &gt; 메뉴바 등이 커짐 </p>
</blockquote>