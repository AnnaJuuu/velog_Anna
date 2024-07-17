<h3 id="어댑터-뷰adapterview">어댑터 뷰(AdapterView)</h3>
<ul>
<li><p>여러개의 항목을 다양한 형식으로 나열하고 선택할 수 있는 기능을 제공하는 view</p>
<ul>
<li>리스트 뷰(ListView) : 항목을 수직으로 나열시키는 방식</li>
<li>그리드 뷰(GridView) : 항목을 격자 형태로 나열시키는 방식</li>
</ul>
</li>
<li><p>대량의 데이터 항목을 효육적으로 표시하기 위해 사용되는 뷰 그룹.</p>
</li>
<li><p>데이터 항목을 동적으로 생성하고, 재사용 가능한 뷰를 통해 화면에 표시한다.</p>
<p>  예) 리스트에 10개의 항목이 있다면 직접 레이아웃을 만들어서 쉽게 구현할 수 있다. 그러나 리스트가 100개, 1000개가 된다면 각각의 항목을 일일이 레이아웃으로 만들면 비효율적이고, 메모리 사용량도 급격히 증가한다. 이럴 때 어댑터 뷰를 통해 뷰를 재사용하면 성능을 크게 향상시킬 수 있다.</p>
</li>
<li><p>어댑터 뷰는 표시할 항목 데이터를 직접 관리하지 않고,어댑터라는 객체로부터 공급받는다.</p>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/cd97b0fc-7961-4e0e-a5b6-65b9a76dad32/image.png" /></p>
<p>데이터 원본을 어댑터를 통해서 가공을 받아서 형식에 맞게 어댑터 뷰 쪽으로 넘겨준다. </p>
<h3 id="어댑터-adapter">어댑터 (Adapter)</h3>
<ul>
<li><p>데이터를 관리하며 데이터 원본과 어댑터 뷰(ListView, GridView)사이의 <strong>중계 역할</strong>한다.</p>
<ol>
<li><p>어댑터 뷰가 어댑터를 사용하기 위해서 : </p>
<p> 먼저 데이터 원본이 어댑터에 설정되어야 하고, 어댑터 뷰에는 어댑터가 설정되어야 함. </p>
</li>
<li><p>어댑터 뷰는 항목을 표시하기 위해서 : </p>
<p> 먼저 표시할 항목의 총 개수를 알 필요가 있을 것이다. </p>
<p> 이 때, 어댑터 뷰는 어댑터의 <strong><code>getCount()</code></strong>란 메소드를 통해 현재 어댑터가 관리하는 데이터 <strong>항목의 총 개수를 반환</strong></p>
</li>
<li><p>어댑터 뷰는 어댑터의 <strong><code>getView()</code></strong>란 메소드를 통해서 <strong>화면에 실제로 표시할 항목뷰를 얻고, 이를 화면에 표시</strong>한다. </p>
</li>
</ol>
</li>
<li><p>사용자가 어댑터뷰의 특정 위치의 항목을 선택하였을 때, 어댑터뷰는 선택된 <strong>항목, 항목ID, 항목뷰</strong>를 어댑터의 <strong>getItem(), getItemId(), getView()</strong> 메소드를 통해 얻어와서 이를 항목선택 이벤트 처리기에 넘겨준다.</p>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/4978e1ae-767f-4d2b-b146-650c16cd0e11/image.png" /></p>
<h3 id="어댑터-종류">어댑터 종류</h3>
<p><strong>1) BaseAdapter</strong></p>
<ul>
<li>어댑터 클래스의 공통 구현</li>
<li>사용자 정의 어댑터 구현 시 사용</li>
</ul>
<p><strong>2) ArrayAdapter</strong></p>
<ul>
<li>객체 배열이나 리소스에 정의된 배열로부터 데이터를 공급받음</li>
</ul>
<p><strong>3) CursorAdapter</strong></p>
<ul>
<li>데이터베이스로부터 데이터를 공급받음</li>
</ul>
<p><strong>4) SimpleAdapter</strong></p>
<ul>
<li>데이터를 Map(키,값)의 리스트로 관리</li>
<li>데이터를 XML파일에 정의된 뷰에 대응시키는 어댑터</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/3481b49f-a192-4ec7-9e28-8a3423335d04/image.png" /></p>
<p>이전에 사용했던 어댑터 코드</p>
<pre><code class="language-kotlin">class FoodListAdapter(private val items: MutableList&lt;FoodInfo&gt;): BaseAdapter()
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