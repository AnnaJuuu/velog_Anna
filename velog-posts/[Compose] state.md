<h3 id="상태와-compose의-구조">상태와 Compose의 구조</h3>
<p>Compose는 <strong>선언형(Declarative) UI 프레임워크</strong></p>
<p>즉, <strong>UI 업데이트는 상태(State)를 변경하는 것</strong>만으로 이루어져.</p>
<blockquote>
<p><strong>❌ 기존 XML 기반 UI</strong></p>
<p>→ 명령형 방식으로 UI 요소를 찾아 수동으로 업데이트해야 함</p>
<p><strong>✅ Compose</strong></p>
<p>→ 상태를 변경하면 Compose가 UI를 자동으로 다시 그림 (재구성)</p>
</blockquote>
<hr />
<h3 id="composition-recomposition">Composition, Recomposition</h3>
<ul>
<li><strong>Composition</strong> : Jetpack Compose가 UI를 처음 생성하는 과정</li>
<li><strong>Recomposition</strong> : 상태(State)가 변경될 때 변경된 부분만 다시 그림</li>
</ul>
<pre><code class="language-kotlin">var name by remember { mutableStateOf(&quot;&quot;) }
// name 값이 변경되면 Recomposition이 발생하고 새로운 UI가 생성됨</code></pre>
<hr />
<h3 id="remember-remembersaveable-rememberupdatedstate">remember, rememberSaveable, rememberUpdatedState</h3>
<table>
<thead>
<tr>
<th><strong>함수</strong></th>
<th><strong>설명</strong></th>
<th><strong>사용 예제</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong><code>remember</code></strong></td>
<td>컴포지션 동안 상태 유지</td>
<td>단순 UI 상태</td>
</tr>
<tr>
<td><strong><code>rememberSaveable</code></strong></td>
<td>회전 등 구성 변경 시 상태 유지</td>
<td>입력값 저장</td>
</tr>
<tr>
<td><strong><code>rememberUpdatedState</code></strong></td>
<td>최신 이벤트 상태 유지</td>
<td>이벤트 리스너</td>
</tr>
</tbody></table>
<p>✅ <strong>remember</strong></p>
<pre><code class="language-kotlin">var count by remember { mutableStateOf(0) }

// 컴포지션 중에만 상태 유지
// 화면 회전 시 초기화됨
</code></pre>
<p>✅ <strong>rememberSaveable</strong></p>
<pre><code class="language-kotlin">var count by rememberSaveable { mutableStateOf(0) }


// 화면 회전 시에도 상태 유지
// Bundle에 저장할 수 있는 값만 가능
</code></pre>
<p>✅ <strong>rememberUpdatedState</strong></p>
<pre><code class="language-kotlin">@Composable
fun TimerExample(onTimeout: () -&gt; Unit) {
    val updatedOnTimeout by rememberUpdatedState(onTimeout)

    LaunchedEffect(Unit) {
        delay(5000)
        updatedOnTimeout()
    }
}

// 최신 이벤트 값을 항상 유지
</code></pre>