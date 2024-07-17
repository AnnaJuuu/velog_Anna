<p>ListView는 어댑터 뷰의 대표 위젯으로서, 복수 개의 항목을 수직으로 표시</p>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/05ee86c6-8816-46b5-bc46-f5eb6929e227/image.png" /></p>
<h3 id="실습">실습</h3>
<h3 id="1-xml파일">(1) xml파일</h3>
<ul>
<li>메인 화면 레이아웃에 ListView위젯을 추가</li>
<li>xml레이아웃 파일에 정의된 ListView 위젯을 Java코드에서 참조하기 위하여 id속성을 정의한다.</li>
</ul>
<pre><code class="language-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;LinearLayout xmlns:android=&quot;http://schemas.android.com/apk/res/android&quot;
    android:orientation=&quot;vertical&quot;
    android:layout_width=&quot;match_parent&quot;
    android:layout_height=&quot;match_parent&quot;&gt;

    &lt;ListView
        android:id=&quot;@+id/listView&quot;
        android:layout_width=&quot;match_parent&quot;
        android:layout_height=&quot;match_parent&quot;
       /&gt;
&lt;/LinearLayout&gt;</code></pre>
<h3 id="2-어댑터-객체-생성">(2) 어댑터 객체 생성</h3>
<ul>
<li>데이터 원본이 배열인 경우 ArrayAdapter객체 사용</li>
<li>ArrayAdapter(Context context, int resource, int textViewResourceId, T[] objects)<ul>
<li>context : 현재 컨텍스트</li>
<li>resource : 항목으로 표시될 텍스트 뷰의 리소스 ID</li>
<li>objects : 어댑터로 공급될 데이터 원본으로 단순 배열</li>
</ul>
</li>
</ul>
<p><img alt="업로드중.." src="blob:https://velog.io/efacecb0-fadb-475e-9fbd-780631c538a2" /></p>
<p>String 배열을 이용한 ArrayAdapter객체 생성 </p>
<pre><code class="language-kotlin">class MainActivity : AppCompatActivity() {

    private lateinit var binding: ActivityMainBinding

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        binding = ActivityMainBinding.inflate(layoutInflater)
        setContentView(binding.root)

        // 데이터 원본 준비
        val items = arrayOf&lt;String?&gt;(&quot;item1&quot;, &quot;item2&quot;, &quot;item3&quot;, &quot;item4&quot;, &quot;item5&quot;, &quot;item6&quot;, &quot;item7&quot;, &quot;item8&quot;, &quot;item5&quot;, &quot;item6&quot;, &quot;item7&quot;, &quot;item8&quot;, &quot;item5&quot;, &quot;item6&quot;, &quot;item7&quot;, &quot;item8&quot;, &quot;item5&quot;, &quot;item6&quot;,  &quot;item7&quot;, &quot;item8&quot;)

        //어댑터 준비 (배열 객체 이용, simple_list_item_1 리소스 사용
        val adapter = ArrayAdapter(this, android.R.layout.simple_list_item_1, items)

        // (3) 어댑터를 ListView 객체에 연결
        binding.listView.adapter = adapter

    }
}</code></pre>
<h3 id="3-listview객체에-어댑터-연결">(3) ListView객체에 어댑터 연결</h3>
<ul>
<li>현재 화면 레이아웃(activity_main.xml)에 정의 된 뷰 중에서 id가 listView인 ListView   객체를 ViewBinding을 통해서 얻어온다.</li>
<li>얻어온 ListView객체에 생성된 어댑터 객체(예,ArrayAdapter객체-adapter)를 연결한다</li>
</ul>
<hr />
<h3 id="이전에-썼던-listview">이전에 썼던 listview</h3>
<p><strong>data class</strong></p>
<pre><code class="language-kotlin">package com.example.menujo.data

import android.graphics.drawable.Drawable

data class FoodInfo(
    val foodId : Int,
    val name : String,
    val introduce : String,
    val tags: List&lt;String&gt;,
)</code></pre>
<p><strong>매니저</strong></p>
<pre><code class="language-kotlin">object FoodManager {
    var foodList = initFoodData()
    private fun initFoodData(): MutableList&lt;FoodInfo&gt; {
        return mutableListOf(
            FoodInfo(
                1,
                &quot;짜장면&quot;,
                &quot;맛있음&quot;,
                listOf(&quot;중간맛&quot;, &quot;야채&quot;)
            ),
            FoodInfo(
                2,
                &quot;탕수육&quot;,
                &quot;맛있음&quot;,
                listOf(&quot;중간맛&quot;, &quot;야채&quot;)
            ),
            FoodInfo(
                3,
                &quot;???&quot;,
                &quot;맛있음&quot;,
                listOf(&quot;중간맛&quot;, &quot;야채&quot;)
            ))
    }
}</code></pre>
<p><strong>어댑터</strong></p>
<pre><code class="language-kotlin">package com.example.menujo

import android.view.LayoutInflater
import android.view.View
import android.view.ViewGroup
import android.widget.BaseAdapter
import android.widget.TextView
import com.example.menujo.data.FoodInfo

class FoodListAdapter(private val items: MutableList&lt;FoodInfo&gt;): BaseAdapter()
{
    override fun getCount(): Int = items.size

    override fun getItem(position: Int): FoodInfo = items[position]

    override fun getItemId(position: Int): Long = position.toLong()

    override fun getView(position: Int, view: View?, parent: ViewGroup?): View {
        var convertView = view
        if (convertView == null) convertView = LayoutInflater.from(parent?.context).inflate(R.layout.item_food, parent, false)

        val item: FoodInfo = items[position]
        convertView!!.findViewById&lt;TextView&gt;(R.id.tv_menu_list_name).text = item.name
        convertView!!.findViewById&lt;TextView&gt;(R.id.tv_menu_list_intoduce).text = item.introduce


        return convertView
    }
}</code></pre>