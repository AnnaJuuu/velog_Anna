<p>View &amp; parent 서로 간의 위치 관계를 ****지정하여 배치</p>
<h2 id="주요-속성">주요 속성</h2>
<p>상대 View의 위치를 기준으로 정렬하는 Layout 클래스이다. </p>
<p><code>@+id/아이디</code> 각 속성에 입력하는 값은 기준이 되는 view 의 id이다</p>
<h3 id="androidlayout_-기준-뷰의"><code>android:layout_</code> 기준 뷰의</h3>
<p><strong><code>above</code></strong>위쪽에 배치</p>
<p><strong><code>below</code></strong>아래쪽에 배치</p>
<p><strong><code>toLeftOf</code></strong> 왼쪽에 배치</p>
<p><strong><code>toRightOf</code></strong> 오른쪽에 배치</p>
<hr />
<p><strong><code>alignTop</code></strong> 위쪽을 맞춤</p>
<p><strong><code>alignBottom</code></strong> 아래쪽을 맞춤</p>
<p><strong><code>alignLeft</code></strong>왼쪽을 맞춤</p>
<p><strong><code>alignRight</code></strong>오른쪽을 맞춤</p>
<p><strong><code>alignBaseline</code></strong>텍스트 기준선을 맞춤</p>
<img src="https://velog.velcdn.com/images/a700hui/post/a85f523e-c3e6-4ef6-b9d2-584fa366f0a5/image.png" width="10%" />


<h3 id="parent의-주요-속성">Parent의 주요 속성</h3>
<h3 id="androidlayout_alignparent-부모님의"><code>android:layout_alignParent</code> 부모님의</h3>
<p><strong><code>Top</code></strong> 위쪽에 맞춤</p>
<p><strong><code>Bottem</code></strong>아래쪽에 맞춤</p>
<p><strong><code>Left</code></strong> 왼쪽에 맞춤</p>
<p><strong><code>Right</code></strong> 오른쪽에 맞춤</p>
<hr />
<p><strong><code>android:layout_centerHorizontal</code></strong> : 부모의 가로 방향 중앙에 맞춤</p>
<p><strong><code>android:layout_centerVertical</code></strong> : 부모의 세로 방향 중앙에 맞춤</p>
<p><strong><code>android:layout_centerInParent</code></strong> : 부모의 가로, 세로 중앙에 맞춤</p>
<blockquote>
<p>👀 <strong>true로 변경하면 배치</strong></p>
<p><strong><code>|</code></strong> 사용 ❌❌❌ → 대신 여러 true 가능</p>
<p><strong><code>end</code></strong> right</p>
<p><strong><code>start</code></strong> left</p>
<p><strong><code>Centerln</code></strong> 중앙</p>
</blockquote>
<blockquote>
<p>👀 <strong>layout_alignWithParentlfMissing</strong></p>
<p>다른 view를 정렬 기준으로 설정하였을 경우</p>
<p>기준으로 설정한 view가 없을 때</p>
<p>parent를 기준으로 정렬하게 됨 </p>
</blockquote>
<h3 id="margin">margin</h3>
<p>끝에 얼만큼 띄워라 !</p>
<img src="https://velog.velcdn.com/images/a700hui/post/6ac03b28-47ff-4af5-b3d4-d5490e48b672/image.png" width="50%" />