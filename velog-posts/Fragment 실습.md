<h3 id="fragment-정의하기">Fragment 정의하기</h3>
<p>액티비티를 만들 때와 비슷하게, <strong>하나의 Kotlin 소스 파일과 하나의 XML레이아웃</strong>로 정의</p>
<p><strong>Kotlin소스 파일 생성</strong></p>
<ul>
<li>Fragment를 생성하려면 Fragment의 서브클래스(또는 이의 기존 서브클래스)를 생성</li>
<li>Fragment에 대해 레이아웃을 제공하려면 반드시 onCreateView()콜백 메서드를  구현</li>
<li>inflate()함수를 통해서 fragment_first.xml 파일로부터 레이아웃을 로드</li>
</ul>
<pre><code class="language-kotlin">
class FirstFragment : Fragment() {  
    override fun onCreateView(
        inflater: LayoutInflater, container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View? {
        // Inflate the layout for this fragment
        return inflater.inflate(R.layout.fragment_first, container, false)
    }</code></pre>
<hr />
<p><strong>Fragment를 activity의 레이아웃 파일에 정적 추가</strong></p>
<ul>
<li><p>프래그먼트를 액티비티의 레이아웃 파일 안에서 선언</p>
</li>
<li><p>fragment 안의 android:name 특성은 레이아웃 안에서 인스턴스화할 Fragment 클래스를 지정</p>
<ul>
<li>고유한 ID와 함께 android:id 속성을 제공합니다.</li>
<li>고유한 문자열과 함께 android:tag 속성을 제공합니다.</li>
</ul>
</li>
<li><p>위의 두 가지 중 어느 것도 제공하지 않으면, 시스템은 컨테이너 뷰의 ID를 사용합니다.</p>
</li>
</ul>
<pre><code class="language-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;LinearLayout xmlns:android=&quot;http://schemas.android.com/apk/res/android&quot;
    android:id=&quot;@+id/fragment_container&quot;
    android:layout_width=&quot;match_parent&quot;
    android:layout_height=&quot;match_parent&quot;
    android:orientation=&quot;vertical&quot;&gt;
    &lt;TextView
        android:layout_width=&quot;wrap_content&quot;
        android:layout_height=&quot;wrap_content&quot;
        android:text=&quot;Hello World!&quot; /&gt;
    &lt;fragment
        android:name=&quot;com.skmns.fragmentbasic.FirstFragment&quot;
        android:layout_width=&quot;match_parent&quot;
        android:layout_height=&quot;match_parent&quot;
        android:id=&quot;@+id/fragment&quot; /&gt;
&lt;/LinearLayout&gt;</code></pre>
<hr />
<p><strong>Kotlin 코드에서 동적으로 Fragment 추가하기</strong></p>
<pre><code class="language-kotlin">supportFragmentManager.commit {
            replace(R.id.frameLayout, frag)
            setReorderingAllowed(true)
            addToBackStack(&quot;&quot;)
        }</code></pre>
<ul>
<li><p><strong>supportFragmentManager</strong>
사용자 상호작용에 응답해 Fragment를 추가하거나 삭제하는등 작업을 할 수 있게 해주는 매니저</p>
</li>
<li><p><strong>replace</strong>
어느 프레임 레이아웃에 띄울것이냐, 어떤 Fragment냐</p>
</li>
<li><p><strong>setReorderingAllowed</strong>
애니메이션과 전환이 올바르게 작동하도록 트랜잭션과 관련된 Fragment의 상태 변경을 최적화</p>
</li>
<li><p>addToBackStack
뒤로가기 버튼 클릭시 다음 액션 (이전 fragment로 가거나 앱이 종료되거나)</p>
</li>
</ul>
<blockquote>
<p>👀 <strong>트랜잭션</strong></p>
</blockquote>
<ul>
<li>DB의 상태를 변경시키는 작업의 단위</li>
<li>한꺼번에 수행되어야 할 연산을 모아놓은 것</li>
<li>연산들을 모두 처리하지 못 한 경우에는 원 상태로 복구한다.</li>
</ul>
<hr />
<h2 id="실습">실습</h2>
<p>(1) 버튼을 누르면 fragment 화면이 변경 되는 예제</p>
<p>(2) 아래와 같이 Frag1 버튼을 누르면 프래그먼트 1번 화면이 표시된다.</p>
<p>(3) Frag2 버튼을 누르면 프래그먼트 2번 화면이 표시된다.</p>
<img src="https://velog.velcdn.com/images/a700hui/post/6c4b3cae-c675-4fd5-9da3-daa16340ed45/image.png" width="40%" /> 


<h3 id="fragment">Fragment</h3>
<ul>
<li>FragmentExample이라는 프로젝트를 생성</li>
<li>안드로이드스튜디오에서 File &gt; New &gt; Fragment &gt; Fragment(Blank)</li>
</ul>
<img src="https://velog.velcdn.com/images/a700hui/post/9bd51e72-ccbf-40d2-86d4-8a070f24d62a/image.png" width="60%" /> 


<ul>
<li>FragmentName값을 FirstFragement로 설정</li>
<li>FragmentLayoutName값을 fragment_first로 설정</li>
<li>(SecondFragement도 만듬)</li>
</ul>
<img src="https://velog.velcdn.com/images/a700hui/post/712e3d5a-cb90-47e5-86c9-2064a0bcea65/image.png" width="60%" /> 

<h3 id="xml-파일">XML 파일</h3>
<ul>
<li><strong>fragment_first.xml</strong></li>
</ul>
<pre><code class="language-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android=&quot;http://schemas.android.com/apk/res/android&quot;
    xmlns:app=&quot;http://schemas.android.com/apk/res-auto&quot;
    android:layout_width=&quot;match_parent&quot;
    android:background=&quot;#F19B9B&quot;
    android:layout_height=&quot;match_parent&quot;&gt;

    &lt;TextView
        android:layout_width=&quot;wrap_content&quot;
        android:layout_height=&quot;wrap_content&quot;
        android:text=&quot;프v래그먼트 1&quot;
        android:textAllCaps=&quot;false&quot;
        android:textSize=&quot;40sp&quot;
        app:layout_constraintTop_toTopOf=&quot;parent&quot;
        app:layout_constraintStart_toStartOf=&quot;parent&quot;
        app:layout_constraintEnd_toEndOf=&quot;parent&quot;
        app:layout_constraintBottom_toBottomOf=&quot;parent&quot;/&gt;

&lt;/androidx.constraintlayout.widget.ConstraintLayout&gt;</code></pre>
<ul>
<li><strong>fragment_second.xml</strong></li>
</ul>
<pre><code class="language-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android=&quot;http://schemas.android.com/apk/res/android&quot;
    xmlns:app=&quot;http://schemas.android.com/apk/res-auto&quot;
    android:layout_width=&quot;match_parent&quot;
    android:background=&quot;#C785D3&quot;
    android:layout_height=&quot;match_parent&quot;&gt;

    &lt;TextView
        android:layout_width=&quot;wrap_content&quot;
        android:layout_height=&quot;wrap_content&quot;
        android:text=&quot;프래그먼트 2&quot;
        android:textAllCaps=&quot;false&quot;
        android:textSize=&quot;40sp&quot;
        app:layout_constraintTop_toTopOf=&quot;parent&quot;
        app:layout_constraintStart_toStartOf=&quot;parent&quot;
        app:layout_constraintEnd_toEndOf=&quot;parent&quot;
        app:layout_constraintBottom_toBottomOf=&quot;parent&quot;/&gt;

&lt;/androidx.constraintlayout.widget.ConstraintLayout&gt;</code></pre>
<ul>
<li><strong>activity_main.xml (정적)</strong>
fragment를 표시할 FrameLayout과 버튼 2개 추가</li>
</ul>
<pre><code class="language-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;androidx.constraintlayout.widget.ConstraintLayout 
    xmlns:android=&quot;http://schemas.android.com/apk/res/android&quot;
    xmlns:app=&quot;http://schemas.android.com/apk/res-auto&quot;
    xmlns:tools=&quot;http://schemas.android.com/tools&quot;
    android:layout_width=&quot;match_parent&quot;
    android:layout_height=&quot;match_parent&quot;
    tools:context=&quot;.MainActivity&quot;&gt;

    &lt;FrameLayout
        android:id=&quot;@+id/frameLayout&quot;
        android:layout_width=&quot;0dp&quot;
        android:layout_height=&quot;0dp&quot;
        android:layout_marginStart=&quot;10dp&quot;
        android:layout_marginEnd=&quot;10dp&quot;
        app:layout_constraintBottom_toTopOf=&quot;@+id/fragment1_btn&quot;
        app:layout_constraintEnd_toEndOf=&quot;parent&quot;
        app:layout_constraintStart_toStartOf=&quot;parent&quot;
        app:layout_constraintTop_toTopOf=&quot;parent&quot;&gt;
    &lt;/FrameLayout&gt;

    &lt;Button
        android:id=&quot;@+id/fragment1_btn&quot;
        android:layout_width=&quot;0dp&quot;
        android:layout_height=&quot;wrap_content&quot;
        android:layout_margin=&quot;10dp&quot;
        android:text=&quot;Frag1&quot;
        android:textAllCaps=&quot;false&quot;
        app:layout_constraintBottom_toBottomOf=&quot;parent&quot;
        app:layout_constraintEnd_toStartOf=&quot;@+id/fragment2_btn&quot;
        app:layout_constraintStart_toStartOf=&quot;parent&quot;
        app:layout_constraintTop_toBottomOf=&quot;@+id/frameLayout&quot; /&gt;

    &lt;Button
        android:id=&quot;@+id/fragment2_btn&quot;
        android:layout_width=&quot;0dp&quot;
        android:layout_height=&quot;wrap_content&quot;
        android:layout_margin=&quot;10dp&quot;
        android:text=&quot;Frag2&quot;
        android:textAllCaps=&quot;false&quot;
        app:layout_constraintBottom_toBottomOf=&quot;parent&quot;
        app:layout_constraintEnd_toEndOf=&quot;parent&quot;
        app:layout_constraintStart_toEndOf=&quot;@+id/fragment1_btn&quot;
        app:layout_constraintTop_toBottomOf=&quot;@+id/frameLayout&quot; /&gt;

&lt;/androidx.constraintlayout.widget.ConstraintLayout&gt;</code></pre>
<img src="https://velog.velcdn.com/images/a700hui/post/319e1233-7262-4677-b1ed-b00753809873/image.png" width="40%" /> 

<h3 id="mainactivitykt에-fragment-추가">MainActivity.kt에 Fragment 추가</h3>
<p><strong>(1) binding</strong></p>
<pre><code class="language-kotlin">class MainActivity : AppCompatActivity() {

    private val binding by lazy { ActivityMainBinding.inflate(layoutInflater) }

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContentView(binding.root)
    }
}</code></pre>
<p><strong>(2) MainActivity.kt에 Fragment 추가하기 (동적)</strong></p>
<pre><code class="language-kotlin">        binding.apply {
            // 버튼 1 클릭하면 -&gt; 첫번 째 Fragment를 띄워준다.
            fragment1Btn.setOnClickListener {
                setFragment(FirstFragment())
            }
            fragment2Btn.setOnClickListener {
                setFragment(SecondFragment())
            }
        }
        //시작 화면에 FirstFragment를 띄워주기용
        setFragment(FirstFragment())
    }

    private fun setFragment(frag: Fragment) {
        supportFragmentManager.commit {
            //어느 프레임 레이아웃에 띄울것인지
            replace(R.id.frameLayout, frag)
            setReorderingAllowed(true)
            //뒤로가기 버튼 클릭시 다음 액션
            addToBackStack(&quot;&quot;)
        }
    }</code></pre>