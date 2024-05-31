<h3 id="git-branch란">Git Branch란?</h3>
<p>Git branch는 Git에서 코드를 분기하여 관리하는 개념이다. Git에서는 기본적으로 main(master) 하나의 브랜치를 가지고 있다. main브랜치에서 새로운 브랜치를 만들어 작업을 진행하면 기존의 main 브랜치와 <strong>독립적</strong>으로 코드를 변경할 수 있다. 필요에 의해 만들어지는 <strong>각각의 브랜치는 다른 브랜티의 영향을 받지 않다</strong>. </p>
<h3 id="git-branch-기본-사용법">Git Branch 기본 사용법</h3>
<h4 id="1git-branch-이름-생성">1.git branch 이름 생성</h4>
<p><strong><code>git branch anna</code></strong>
새로운 브랜치를 생성하려면, git brach 명령어를 사용해서 뒤에 새로운 이름을 붙여주면 된다.</p>
<h4 id="2-git-branch--m-이름-변경">2. git branch -m 이름 변경</h4>
<p><strong><code>git branch -m kane</code></strong> anna에서 kane으로 브랜치 이름 변경</p>
<h4 id="3-git-branch--d-이름-삭제">3. git branch -d 이름 삭제</h4>
<p><strong><code>git branch -d kane</code></strong> kane 브랜치를 삭제</p>
<h4 id="4-git-checkout-이름-전환">4. git checkout 이름 전환</h4>
<p><strong><code>git checkout main</code></strong> main 브랜치로 전환</p>
<h4 id="5-git-checkout--b-이름-생성-및-전환">5. git checkout -b 이름 생성 및 전환</h4>
<p><strong><code>git checkout -b jonh</code></strong> jonh 브랜치를 생성하고 전환</p>
<h4 id="6-git-merge-이름-병합">6. git merge 이름 병합</h4>
<p><strong><code>git merge main</code></strong> jonh 브랜치의 변경 사항을 main 브랜치에 병합</p>