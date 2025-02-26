<p><strong>상태는 가능한 한 상위 계층에서 관리</strong> 하는 것이 좋음.</p>
<p>이렇게 하면 <strong>Composable 재 사용 가능하게 만들고, 유지 보수를 쉽게 할 수 있음.</strong> </p>
<pre><code class="language-kotlin">@Composable
fun HelloScreen() {
    var name by remember { mutableStateOf(&quot;&quot;) }

    HelloContent(name = name, onNameChange = { name = it })
}

@Composable
fun HelloContent(name: String, onNameChange: (String) -&gt; Unit) {
    Column(modifier = Modifier.padding(16.dp)) {
        if (name.isNotEmpty()) {
            Text(
                text = &quot;Hello, $name!&quot;,
                modifier = Modifier.padding(bottom = 8.dp),
                style = MaterialTheme.typography.bodyMedium
            )
        }

        OutlinedTextField(
            value = name,
            onValueChange = onNameChange,
            label = { Text(&quot;Name&quot;) }
        )
    }
}
</code></pre>
<ul>
<li><code>HelloScreen()</code>에서 <strong>상태를 관리</strong>하고, <code>HelloContent()</code>는 <strong>UI만 담당</strong></li>
<li><code>HelloContent()</code>는 상태를 직접 변경하지 않고, <code>onNameChange</code> 콜백을 호출</li>
<li>재 사용성이 높아지고 유지 보수가 쉬워짐</li>
</ul>