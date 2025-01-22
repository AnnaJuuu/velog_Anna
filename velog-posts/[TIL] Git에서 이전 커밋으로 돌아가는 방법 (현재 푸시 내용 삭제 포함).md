<h3 id="1-이전-커밋-해시-확인">1. 이전 커밋 해시 확인</h3>
<ul>
<li>터미널에서 아래 명령어를 입력하여 이전 커밋의 해시를 확인한다. </li>
</ul>
<pre><code class="language-bash">git log</code></pre>
<ul>
<li>필요한 커밋의 해시를 복사한다. (영어,숫자 부분)</li>
</ul>
<hr />
<h3 id="2-로컬-브랜치를-이전-커밋으로-되돌리기">2. 로컬 브랜치를 이전 커밋으로 되돌리기</h3>
<ul>
<li>아래 명령어를 사용해 현재 브랜치를 이전 커밋 상태로 되돌린다. </li>
</ul>
<pre><code class="language-bash">git reset --hard 해시복사</code></pre>
<ul>
<li>이 명령어는 되돌린 이후의 작업 내용이 모두 삭제된다. 필요 시 미리 백업하기를 사용한다. <code>git stash</code></li>
</ul>
<hr />
<h3 id="3-원격-저장소에-강제로-푸시하기">3. 원격 저장소에 강제로 푸시하기</h3>
<ul>
<li>로컬에서 되돌린 상태를 원격 저장소에도 반영하려면 아래 명령어를 실행한다. </li>
</ul>
<pre><code class="language-bash">git push origin 브랜차 이름 --force</code></pre>
<ul>
<li>브랜치 이름에 현재 작업 중인 브랜치 이름(예: main, develop)을 입력한다. </li>
</ul>
<hr />
<h3 id="주의-사항">주의 사항</h3>
<ul>
<li>강제 푸시는 다른 협업자에게 영향을 줄 수 있으니 팀과 협의 후 진행</li>
<li>삭제된 내용 복구 불가, 신중히 사용</li>
</ul>