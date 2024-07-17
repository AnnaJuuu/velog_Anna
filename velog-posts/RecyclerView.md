<h3 id="recyclerview란">RecyclerView란?</h3>
<p>안드로이드 앱에서 리스트 형태의 데이터를 표시하는데 사용되는 위젯</p>
<p>여러 아이템을 스크롤 가능한 리스트로 표현하며, </p>
<p>많은 아이템을 효율적으로 관리하고 보여주는 역할을 한다. </p>
<ul>
<li><strong>RecyclerView는 한정적인 화면에 많은 데이터를 넣을 수 있는 View</strong></li>
<li><strong>Recycle을 한국어로 하면 재활용하다라는 뜻입니다.</strong></li>
<li><strong>즉, View를 재활용해서 사용하겠다는 말입니다.</strong></li>
</ul>
<h3 id="listview와-recycleview">ListView와 RecycleView</h3>
<p><strong>ListView</strong></p>
<p>사용자가 스크롤 할 때마다 위에 있던 아이템은 삭제되고, 맨 아래의 아이템은 생성 되길 반복한다. </p>
<p>즉, 계속 삭제와 생성을 반복하므로 성능에 좋지않다. </p>
<img src="https://velog.velcdn.com/images/a700hui/post/42136abb-7456-4dcd-b781-a66f1045c084/image.png" width="20%" /> 


<p><strong>RecyclerView</strong></p>
<p>사용자가 스크롤 할 때, 위에 있던 아이템은 재활용 돼서 아래로 이동하여 재사용 한다.</p>
<p>View를 계속 만드는 ListView의 단점을 보완하기 위해 나왔다. </p>
<img src="https://velog.velcdn.com/images/a700hui/post/4011e8ef-6063-4cae-95e9-52e6dc1ccc36/image.png" width="20%" /> 

<h3 id="recyclerview사용">RecyclerView사용</h3>
<p><strong>1) Adapter</strong></p>
<ul>
<li>Adapter란 데이터 테이블을 목록 형태로 보여주기 위해 사용되는 것으로, 데이터를 다양한 형식의 리스트 형식을 보여주기 위해서 <strong>데이터와 RecyclerView 사이에 존재하는 객체</strong>이다.</li>
<li>즉 데이터와 RecyclerView 사이의 통신을 위한 <strong>연결체</strong>이다.</li>
</ul>
<p><strong>2) ViewHolder</strong></p>
<ul>
<li>ViewHolder란 화면에 표시될 데이터나 아이템들을 저장하는 역할</li>
<li>RecyclerView의 개념을 적용하기위해선 스크롤 해서 위로 올라간 View를 재활용하기 위해서 이 View를 기억하고 있어야 한다.. ViewHolder가 그역할을 한다.</li>
</ul>