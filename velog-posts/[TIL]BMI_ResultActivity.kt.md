<h3 id="intent">Intent</h3>
<pre><code class="language-kotlin">        //MainActivity에서 보낸 코드를 ResultActivity에서 받기
        //유저가 메인에서 입력한 신장, 몸무게 값이 결과 페이지로 넘겨줌
        val height = intent.getIntExtra(&quot;height&quot;, 0)
        val weight = intent.getIntExtra(&quot;weight&quot;, 0)</code></pre>
<h3 id="bmi-계산">BMI 계산</h3>
<p>round()는 반올림을 해주는 함수다. </p>
<pre><code class="language-kotlin">        //BMI 계산
        var BMIvalue = weight / (height/100.0).pow(2.0)
        BMIvalue = round(BMIvalue*10)/10

        var resultText =&quot;&quot;
        var resImage = 0
        var resColor = 0

        if(BMIvalue &lt; 18.5)
        {
            resultText = &quot;저체중&quot;
            resImage = R.drawable.lv2
            resColor = Color.YELLOW
        } else if (BMIvalue &gt;= 18.5 &amp;&amp; BMIvalue &lt; 23.0)
        {
            resultText = &quot;정상체중&quot;
            resImage = R.drawable.lv1
            resColor = Color.GREEN
        } else if (BMIvalue &gt;= 23.0 &amp;&amp; BMIvalue &lt; 25.0)
        {
            resultText = &quot;과제중&quot;
            resImage = R.drawable.lv3
            resColor = Color.BLACK
        } else if (BMIvalue &gt;= 25.5 &amp;&amp; BMIvalue &lt; 30.0)
        {
            resultText = &quot;경도 비만&quot;
            resImage = R.drawable.lv4
            resColor = Color.CYAN
        } else if (BMIvalue &gt;= 30.0 &amp;&amp; BMIvalue &lt; 35.0)
        {
            resultText = &quot;중정도 비만&quot;
            resImage = R.drawable.lv5
            resColor = Color.MAGENTA
        } else
        {
            resultText = &quot;고도 비만&quot;
            resImage = R.drawable.lv6
            resColor = Color.RED
        }</code></pre>
<h3 id="아이디-연결-계산-값을-넣기-종료">아이디 연결, 계산 값을 넣기, 종료</h3>
<pre><code class="language-kotlin">        //아이디들 찾아서 변수에 연결하기
        val tv_resValue = findViewById&lt;TextView&gt;(R.id.tv_resValue)
        val tv_resText = findViewById&lt;TextView&gt;(R.id.tv_restText)
        val iv_image = findViewById&lt;ImageView&gt;(R.id.iv_image)
        val btn_back = findViewById&lt;Button&gt;(R.id.btn_back)

        //tv_resValue에 계산한 값을 넣어주기
        tv_resValue.text = BMIvalue.toString()
        tv_resText.text = resultText
        iv_image.setImageResource(resImage)
        tv_resText.setTextColor(resColor)

        //돌아가기 누르면 바로 종료
        btn_back.setOnClickListener {
            finish()</code></pre>