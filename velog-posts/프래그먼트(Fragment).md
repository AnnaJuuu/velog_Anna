<h3 id="프래그먼트fragment란">프래그먼트(Fragment)란?</h3>
<ul>
<li>액티비티 위에서 동작하는 모듈화된 사용자 인터페이스<ul>
<li>액티비티와 분리되어 <strong>독립적으로 동작할 수 없음</strong></li>
</ul>
</li>
<li>여러 개의 프래그먼트를 하나의 액티비티에 조합하여 창이 여러 개인UI를 구축할 수 있으며,</li>
<li>하나의 프래그먼트를 여러 액티비티에서 <strong>재 사용</strong>할 수 있음</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/592fb730-9221-4189-a53c-8505c60f6105/image.png" /></p>
<blockquote>
<p>👀 <strong>생명주기</strong></p>
</blockquote>
<ul>
<li>시스템에서 클래스 객체의 생명주기를 관리하는 것을 컴포넌트 클래스라고 한다.</li>
<li>Fragment 역시 개발자가 생명주기를 관리하지 않는다.</li>
<li>개발자가 코드로 직접 Fragment의 추가나 제거, 교체같은 작업을 요청하더라도</li>
<li>시스템에 요청을 통해 진행되기 때문에 개발자가 직접 Fragment 객체의 생명주기에 관여하지 않는다.</li>
<li>즉, <strong>시스템이 Fragment 객체의 생명주기를 관리</strong>합니다.</li>
</ul>
<blockquote>
<p>👀 <strong>그럼 Fragment는 컴포넌트 클래스인가?  → 놉 아님.</strong></p>
</blockquote>
<ul>
<li>Fragment는 해당 Fragment를 선언한 activity에 종속되어 있기 때문에<ul>
<li>생명주기는 항상 activity를 통해 간접적으로 관리 된다.</li>
</ul>
</li>
<li>따라서 Fragment는 독립적으로 존재할 수 없다.</li>
<li>즉, <strong>앱의 진입점이 될 수 없는 것</strong>이다.</li>
<li>앱의 구성요소인 컴포넌트의 조건을 충족할 수 없기 때문에 컴포넌트라고 할 수 없다.</aside>

</li>
</ul>
<h3 id="activity의-문제점-보완">Activity의 문제점 보완</h3>
<blockquote>
<p>현재의 activity가 하나의 화면을 나타내다보니 똑같은 UI를 가지고 있지만 콘텐츠가 다른 경우</p>
<p>→ 해당 화면을 위해 비슷한 코드의 새로운 activity를 생성해야함 </p>
<p>디바이스가 다양해지면서 화면의 크기도 천차만별로 달라짐 </p>
<p>(태블릿 PC는 스마트폰의 화면에 비해 상당히 큰 화면을 가지고 있다. )</p>
<p>즉, 최적화를 위해 화면에 한 개 이상의 UI를 그려야 한다. </p>
<p>하지만 activity는 화면 하나만 나타내는 것이 가능하기 때문에 이러한 부분에서 큰 어려움을 가지고 있다. </p>
</blockquote>
<ul>
<li>Fragment는 이러한 문제점을 해결할 수 있다.</li>
<li>Fragment는 <strong>UI를 모듈 형식으로 나누어 관리</strong>할 수 있도록 해주는 클래스로,</li>
<li>화면의 <strong>일부분만 차지</strong>하기 때문에 <strong>하나의 activity에 여러 개의 Fragment를 사용</strong>할 수 있다.</li>
<li>전체를 덮는다고 해도 전체 ‘<strong>면적</strong>’만 차지할 뿐, 화면 자체를 차지하는게 아니라는 의미</li>
<li>컴포넌트 클래스가 아니기 때문에 각각의 클래스가 독립성을 지니지 않아</li>
<li>UI가 똑같은 화면의 경우 Fragment를 <strong>재사용</strong>해 불필요한 액티비티를 생성할 필요 없이 화면을 구성</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/56b1b8f6-815b-40be-bb76-386177afe0f1/image.png" /></p>
<blockquote>
<p>👀 <strong>Fragment만 써도 됨? → 놉 안됨.</strong></p>
</blockquote>
<ul>
<li>Fragment는 activity에 종속된 클래스이기 때문에 반드기 activity 내에서만 사용가능</li>
<li>생명주기 또한 activity에 중속되어 단독으로 사용하는 것은 불가능</li>
<li>한마디로 정라히자면 : <strong>activity라는 화면이 있어야 Fragment라는 UI의 조각을 붙일 수 있는 것</strong></li>
</ul>
<h3 id="activity-vs-fragment">Activity VS Fragment</h3>
<p>activity는 안드로이드 앱의 화면을 구성하는 구성요소</p>
<p>Fragment는 activity에 종속된 화면의 전체 혹은 일부를 표시하는 구성요소</p>
<ul>
<li>activity</li>
</ul>
<p>시스템의 activity 매니저에서 <strong>intent</strong>를 해석해 activity간 데이터를 전달</p>
<ul>
<li>Fragment</li>
</ul>
<p>activity의 Fragment 매니저에서 <strong>메소드</strong>로 Fragment간 데이터를 전달</p>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/f79a8ccf-5ff5-4b49-ad4c-c0de2a3a6df4/image.png" /></p>
<blockquote>
<p>❓ Fragment는 자체 레이아웃을 가질 수 있으며 자체 생명 주기를 보유한다.
<del>❓ 시스템에서 관리하는데 자체 생명주기를 보유한다?</del> 
→ 생명주기 보유하지 않는 뷰가 없다. 좀 어렵게 설명한거 뿐</p>
</blockquote>
<h3 id="fragment-사용하는-이유-정리">Fragment 사용하는 이유 정리</h3>
<ol>
<li><p>Fragment를 사용하면 activity를 적게 만들 수 있다.</p>
</li>
<li><p>activity의 <strong>복잡도를 줄일 수 있다</strong>.</p>
</li>
<li><p>Fragment를 사용하면 <strong>재사용할 수 있는 레이아웃을 분리해서 관리가 가능</strong>하다. </p>
</li>
<li><p>Fragment를 사용하면 최소 1개의 activity안에서 Fragment 공간에 View만 집어넣으면 </p>
<p> 여러 activity를 만들지 않아도 여러 화면을 보여줄 수 있다.</p>
</li>
</ol>