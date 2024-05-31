<p>오늘은 로또 번호 생성하는 앱을 만들어 보려고 한다. 완성 후에 한번 자동으로 돌려서 사보려고 한다.ㅋㅋ</p>
<h3 id="xml">XML</h3>
<blockquote>
<pre><code class="language-xml">&lt;?xml versoin = &quot;1.0&quot; encoding = &quot;utf-8&quot;?&gt;
&lt;shape xmlns:android=&quot;http://schemas.android.com/apk/res/android&quot;
    android:shape=&quot;oval&quot;&gt;
    &lt;solid
        android:color=&quot;#FFE900&quot;/&gt; 
    &lt;size
        android:width=&quot;44dp&quot;
        android:height=&quot;44dp&quot;/&gt;
&lt;/shape&gt;</code></pre>
</blockquote>
<pre><code>
&gt;```
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;shape xmlns:android=&quot;http://schemas.android.com/apk/res/android&quot;
    android:shape=&quot;rectangle&quot;&gt;
    &lt;solid
        android:color=&quot;#D6EDEB&quot;/&gt;
    &lt;stroke
        android:width=&quot;1dp&quot;
        android:color=&quot;#000000&quot;/&gt;
&lt;/shape&gt;</code></pre><p>위 코드로 작성하면 다음 화면을 구성할 수 있다. </p>
<img src="https://velog.velcdn.com/images/a700hui/post/c50694b8-f547-4a59-a4b0-ccc35e03fa28/image.png" width="20%" />

<p><strong><code>shape 모양 지정</code></strong>
oval : 타원형          (android:shape=&quot;oval&quot;)
rectangle : 사각형    (android:shape=&quot;rectangle&quot;)
line : 선               (android:shape=&quot;line&quot;)</p>
<p><strong><code>스타일</code></strong>
solid : 단색으로 채워넣기
gradient : 시작 color로부터 끝나는 color를 지정하여 그라디언트 효과 주기
stroke : 테두리 그려넣기
corners : 가장자리를 둥글게 처리
padding : 패딩처리</p>
<h3 id="이미지-뷰-넣기">이미지 뷰 넣기</h3>
<p>BMI 계산기 레이아웃은 다자인 화면에서 끌어다 놓는 방식으로 진행했었는데, 이번에는 xml파일에 직접 작성했다. 나는 개인적으로 xml파일이 더 좋다. 약간 코딩 짱 잘하는거 같아서 ... 좋다 ...</p>
<pre><code class="language-xml">    &lt;ImageView
    &lt;!-- 가로, 새로 높이 및 사진 추가 --&gt;
        android:layout_width=&quot;300dp&quot;
        android:layout_height=&quot;100dp&quot;
        android:src=&quot;@drawable/ic_lotto&quot;
    &lt;!-- 레이아웃 --&gt;
        android:layout_marginTop=&quot;30dp&quot;
        app:layout_constraintEnd_toEndOf=&quot;parent&quot;
        app:layout_constraintStart_toStartOf=&quot;parent&quot;
        app:layout_constraintTop_toTopOf=&quot;parent&quot;
        /&gt;</code></pre>
<p>위 코드로 작성하면 다음 화면을 구성할 수 있다. </p>
<img src="https://velog.velcdn.com/images/a700hui/post/725b5ce2-f37e-4e6a-a46d-253d513b46ad/image.png" width="40%" />

<h3 id="색상">색상</h3>
<pre><code class="language-xml">  &lt;NumberPicker
        &lt;!-- id 이름 정하기--&gt;
        android:id=&quot;@+id/np_num&quot;
        android:layout_width=&quot;wrap_content&quot;
        android:layout_height=&quot;wrap_content&quot;
        android:layout_marginTop=&quot;38dp&quot;
        &lt;!-- 중간 : 백그라운드 보라 색상--&gt;
        android:background=&quot;@android:color/holo_purple&quot;
        &lt;!-- 위 아래 : 파랑 색상--&gt;
        android:solidColor=&quot;#4cafff&quot;
        app:layout_constraintStart_toStartOf=&quot;parent&quot;
        app:layout_constraintTop_toBottomOf=&quot;@+id/textView&quot; /&gt;</code></pre>
<p>위 코드로 작성하면 다음 화면을 구성할 수 있다. </p>
<img src="https://velog.velcdn.com/images/a700hui/post/b126e4db-068a-40ba-82df-26b6db42c950/image.png" width="10%" />


<pre><code class="language-xml">    &lt;LinearLayout
        android:layout_width=&quot;match_parent&quot;
        android:layout_height=&quot;80dp&quot;
        android:layout_marginStart=&quot;16dp&quot;
        android:layout_marginEnd=&quot;16dp&quot;
        android:background=&quot;@drawable/bg&quot;
        app:layout_constraintEnd_toEndOf=&quot;parent&quot;
        app:layout_constraintStart_toStartOf=&quot;parent&quot;
        app:layout_constraintTop_toBottomOf=&quot;@+id/np_num&quot;

        /&gt;</code></pre>