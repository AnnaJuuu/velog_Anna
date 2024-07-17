<h3 id="뷰-바인딩view-binding이란">뷰 바인딩(View Binding)이란</h3>
<ul>
<li>View Binding은 View와 상호작용하는 코드를 쉽게 해주는 기능이다.</li>
<li>View Binding을 허용하면 각 xml레이아웃마다 <strong>Binding 클래스</strong>를 자동으로 생성하는데,</li>
<li>레이아웃에 ID가 있는 View에 직접 참조를 할 수 있다.</li>
<li>대부분의 상황에서 View Binding은 findViewById를 대체한다.</li>
</ul>
<h3 id="findviewbyid와의-차이점">findViewById와의 차이점</h3>
<p>View 결합에는 <code>findViewById</code>를 사용하는 것에 비해 다음과 같은 중요한 장점이 있다.</p>
<ul>
<li><strong>Null 안전성(null-safety)</strong><ul>
<li>View 결합은 View의 직접 참조를 생성하므로 잘못된 View ID로 인해 null 포인터 예외가 발생할 위험이 없다.</li>
<li>또한 View가 레이아웃의 일부 구성에서만 존재하는 경우 결합 클래스에 참조가 포함된 필드가 <code>@Nullable</code>로 표시된다.</li>
</ul>
</li>
<li><strong>유형 안전성(type-safety)</strong><ul>
<li>각 바인딩 클래스의 필드에는 XML 파일에서 참조하는 View와 일치하는 유형이 있다. 즉, 클래스 변환 예외가 발생할 위험이 없습니다.</li>
<li>쉽게 말하면, 타입을 가지고 있기 때문에 imageView.text 같이 타입이 다른 경우 발생하는 오류를 방지할 수 있다.</li>
</ul>
</li>
</ul>
<p>이러한 차이점은 레이아웃과 코드 간의 비호환성으로 인해 런타임이 아닌 컴파일 시간에 빌드가 실패한다는 것을 의미한다.</p>
<p>즉, 컴파일에서 빌드가 실패하므로 우리가 오류를 찾기 더 쉽다.</p>
<h3 id="설정">설정</h3>
<p>뷰 바인딩은 모듈별로 사용 설정된다. </p>
<p>→ 모듈 수준 <code>build.gradle</code> 파일에서 <code>viewBinding</code> 빌드 옵션을 <code>true</code>로 설정</p>
<pre><code class="language-xml">android {
    ...
    buildFeatures {
        viewBinding = true
    }
}</code></pre>
<p>viewBinding은 gradle에 설정하는 것 만으로 개발자가 작성한 레이아웃 파일들을 다음과 같은 공식으로 모두 바인딩클래스로 자동변환 해줌</p>
<pre><code class="language-xml">&lt;!-- 자동변환공식 : 레이아웃파일명(첫 글자와 언더바 다음영문을 대문자로 변환) + Binding --&gt;
&lt;!-- 예) --&gt;
activity_main.xml = ActivityMainBinding
activity_sub.xml = ActivitySubBinding
item_recycler.xml = ItemRecyclerBinding</code></pre>
<h3 id="특정-파일-무시">특정 파일 무시</h3>
<p>→ <code>tools:viewBindingIgnore=&quot;true&quot;</code> 속성을 레이아웃 파일의 루트 View에 추가</p>
<pre><code class="language-xml">&lt;LinearLayout
        ...
        tools:viewBindingIgnore=&quot;true&quot; &gt;
    ...
&lt;/LinearLayout&gt;</code></pre>
<blockquote>
<p>👀 <code>tools:viewBindingIgnore=&quot;true&quot;</code></p>
<p>속성은 Android의 View Binding 기능을 사용할 때, 
특정 XML 레이아웃 파일을 View Binding이 무시하도록 지시하는 것
View Binding을 사용하면 각 XML 레이아웃 파일에 대해 결합 클래스가 자동 생성되는데, 
때로는 특정 상황에서 이 생성을 원하지 않을 수 있다.</p>
</blockquote>
<h3 id="activity에서-view-binding-사용">Activity에서 View Binding 사용</h3>
<p>Activity에 사용할 결합 클래스 인스턴스를 설정하려면 <strong><code>onCreate()</code></strong>메서드에서 </p>
<ol>
<li><p>생성된 클래스에 포함된 정정 <strong><code>inflate()</code></strong> 메서드를 호출</p>
<p> 그러면 Activity에서 사용할 결합 클래스 인스턴스가 생성됨 </p>
</li>
<li><p><strong><code>getRoot()</code></strong> 메서드를 호출하거나 Kotlin 속성 문법을 사용하여 루트 뷰 참고를 가져온다. </p>
</li>
<li><p>루트 뷰를 <strong><code>setContentView()</code></strong>에 전달하여 화면의 활성 뷰로 만듬</p>
</li>
</ol>
<pre><code class="language-kotlin">class MainActivity : AppCompatActivity() {

    private lateinit var binding: ActivityMainBinding

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        binding = ActivityMainBinding.inflate(layoutInflater) 
        setContentView(binding.root)

        binding.myButton.setOnClickListener{
            binding.myTextView.text = &quot;바인딩이 잘 되네요!&quot;
        }
    }
}</code></pre>
<p><strong><code>inflate()</code></strong></p>
<p>xml 레이아웃 파일을 메모리에 로드하고, 그 안에 있는 모든 뷰들을 결합 클래스의 인스턴스로 반환</p>
<p><strong><code>getRoot()</code></strong></p>
<p>로드된 XML 레이아웃의 루트 뷰(root view)를 가져옴</p>
<p><strong><code>Kotlin 속성 문법</code></strong></p>
<p>속성(property)문법을 사용하여 루트 뷰에 직접 접근할 수도 있다. </p>
<p><strong><code>setContentView()</code></strong></p>
<p>Activity나 Fragment에서 화면에 표시할 뷰를 설정할 때, </p>
<p><code>setContentView()</code> 메서드를 호출하거나 </p>
<p>Fragment에서는 <code>onCreateView()</code> 메서드에서 반환하는 뷰를 설정</p>
<p>이 때, 결합 클래스에서 가져온 루트 뷰를 <code>setContentView()</code>에 전달하거나 Fragment에서 반환하여 화면에 해당 뷰를 표시함</p>
<blockquote>
<p>👀 <strong>로드된 XML 레이아웃의 루트 뷰(root view)를 가져온다</strong></p>
<p><strong><code>로드</code></strong> </p>
<p>xml 파일을 메모리에 읽어오는 것을 의미한다. 
Android 애플리케이션에서는 XML 레이아웃 파일에 UI 요소들을 정의하고,
이를 앱에서 실제로 사용하기 위해서는 이 파일을 메모리에 로드해서 뷰 객체로 변환해야 함</p>
<p><strong><code>로드 과정</code></strong></p>
<ul>
<li><p><strong>XML 파일 읽기</strong> : View Binding을 사용하면 Android 시스템이 지정된 XML 레이아웃 파일을 읽어와서 뷰 객체로 변환.
이 과정에서 XML 파일의 내용을 이해하고 각 요소들을 식별한다. </p>
</li>
<li><p><strong>뷰 객체 생성</strong> : XML 파일을 메모리에 로드하면, 각 UI 요소(버튼, 텍스트뷰 등)들은 뷰 객체로 생성됨.
이들 뷰 객체는 앱에서 직접적으로 조작할 수 있는 UI 요소다.</p>
</li>
</ul>
<hr />
<p><strong><code>루트 뷰(root view)</code></strong></p>
</blockquote>
<p>xml 레이아웃 파일에서 가장 상위에 있는 뷰를 말한다. 
예) LinearLayout, ConstraintLayout 같은 레이아웃 요소가 있을 때
이들의 레이아웃 파일의 상위 계층을 형성하며 앱 화면의 기본 구조를 결정</p>
<blockquote>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/e6340f1d-265b-4ec7-9ae4-81e3a11e1a46/image.png" /></p>
<blockquote>
<hr />
<p><strong><code>결론</code></strong></p>
</blockquote>
<p>ViewBinding을 사용하여 xml파일을 메모리에 로드하고, 
그 파일의 가장 상위에 있는 뷰 객체(일반적으로는 레이아웃 요소)를 참조한다는 의미.
이 뷰 객체를 통해 앱에서 해당 레이아웃을 구성하고, 
필요에 따라 내부의 다른 뷰들에 접근하거나 조작할 수 있다. </p>