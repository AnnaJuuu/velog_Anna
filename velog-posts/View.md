<img src="https://velog.velcdn.com/images/a700hui/post/416e32ca-bc13-47cc-8c3a-ba3944ffa039/image.png" />

<ul>
<li>안드로이드에서 눈에 보이는 모든 요소를 View라고 부른다.</li>
<li>개발자가 배치하는 모든 View 들은 Class로 제공됨<ul>
<li>View 클래스는 모든 UI 요소들의 부모 클래스 . </li>
</ul>
</li>
</ul>
<blockquote>
<p>👀 <strong>View</strong></p>
<p>View클래스 안에 다양한 ui요소 들이 화면상에 보여줄 수 있는 기본적인 기능들이 구현 되어져 있다. </p>
<p>이 기본적인 기능들 상속 받아서 다양한 화면과 관련된 클래스를 만들어서 제공</p>
</blockquote>
<p><strong><code>Widget</code> + <code>Layout</code> = View</strong></p>
<h2 id="layout">Layout</h2>
<p>Container, View Group 이라고 부르기도 한다. </p>
<p><strong><code>Container</code></strong> View들을 포함</p>
<p><strong><code>View Group</code></strong> 내부의 View를 통합 관리</p>
<p><strong><code>Layout</code></strong> 내부 View 들이 배치되는 모양을 결정한다.</p>
<img src="https://velog.velcdn.com/images/a700hui/post/1a2f7fba-2a15-41a4-b91f-956b7805e452/image.png" width="60%" />

<p>안드로이드는 좌표가 아닌 배치되는 모양을 결정하게 된다.</p>
<p>View들을 배치하면 안드로이드 OS가 단말기에 적합한 좌표를 계산하고 View들을 배치하게 된다.</p>
<img src="https://velog.velcdn.com/images/a700hui/post/2712a7b7-30d3-4676-9097-0e29e256f9b0/image.png" width="30%" />

<p>예) 가운데에 배치 → 작은 곳에서도 가운데 배치. 짤리는 현상 없음</p>
<h3 id="parent와-child">Parent와 Child</h3>
<p>안드로이드는 화면을 구성하기 위해 Layout을 먼저 배치하고 그 위에 다른 View들을 배치하게 된다.</p>
<p><code>Layout → Parent</code></p>
<p><code>View →  Child</code></p>
<p>모든 View 들은 단 하나의 Parent</p>
<p>모든 Layout → 다수의 Child를 가질 수 있음.</p>
<img src="https://velog.velcdn.com/images/a700hui/post/78ec15d8-c35c-4c7a-8978-9844d9be3fe0/image.png" width="20%" />


<h3 id="레이아웃-종류">레이아웃 종류</h3>
<img src="https://velog.velcdn.com/images/a700hui/post/09a90b37-6599-43a0-8c1c-fae465554eaf/image.png" width="80%" />


<h2 id="widget">Widget</h2>
<p>문자열 입력, 문자열 출력 등 어떤 기능을 가지고 있고 사용자와 상호 작용을 하는 View들을 통칭</p>
<p>(버튼, 입력상자 등)</p>
<h3 id="화면-만들기">화면 만들기</h3>
<p>화면에 layout을 배치하고 그 안에 다른 layout이나 widget을 배치하여 화면의 모양을 만든다. </p>
<p>이렇게 만들어진 화면은 모두 객체로 생성되므로 개발자는 이 객체들을 이용해 코드에서 필요한 작업을 할 수 있다.</p>
<blockquote>
<p>👀 <strong>View의 주요 속성</strong>
<strong><code>id</code></strong> xml이나 코드에서 View를 지칭하기 위해 사용하는 속성</p>
<p><strong><code>layout_width</code></strong> View의 가로 길이</p>
<p><strong><code>layout_height</code></strong> View의 세로 길이</p>
<p><strong><code>layout_matgin</code></strong> View의 외부 여백 (상하좌우)</p>
<p><strong><code>padding</code></strong> View의 내부 여백</p>
<p><strong><code>backgroung</code></strong> View의 배경 지정</p>
</blockquote>
<blockquote>
<p>👀 <strong>layout 사이즈</strong></p>
<p><strong><code>match_parent</code></strong> 배치된 layout과 같은 사이즈로</p>
<p><strong><code>weap_content</code></strong> 최소 사이즈 </p>
</blockquote>