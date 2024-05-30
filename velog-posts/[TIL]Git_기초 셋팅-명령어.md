<h3 id="git이란">Git이란?</h3>
<p>Git은 <strong>컴퓨터 파일의 변화를 추적</strong>하고 여러 사람들 사이에서 그 파일을 조정하는 <span style="background-color: yellow;">버전 관리 시스템</span>이다. 이것은 다시 말해서 Git의 가장 기본적인 중요한 기능이 여러 팀에서 <strong>동시에 같은 프로젝트로 코드를 통합하게 허용</strong>한다는 걸 의미한다. 이러한 능력을 프로젝트에 더함으로써 팀을 더 효율적이게 하고 더 큰 규모의 프로젝트나 더 복잡한 문제들에 일할 수 있는 능력을 제공한다. </p>
<h3 id="git의-장점">Git의 장점</h3>
<ul>
<li>유지보수</li>
<li>저장 용량</li>
<li>언제 어떤 코드가 수정되었는지 확인(추적광리)</li>
<li>코드 공유(코드 저장, 만약 파일이 저장된 노트북을 잃어버린다면!!!??)</li>
<li>버전 관리</li>
</ul>
<h3 id="git-기초-셋팅-명령어">Git 기초 셋팅 명령어</h3>
<p>오늘 배운 명령어와 내가 알고 있는 초기셋팅들 위주로 먼저 정리해 보겠다.
가장 먼저<span style="background-color: yellow;">Git 버전</span>을 확인해 보겠다. 
<strong><code>git --version</code></strong></p>
<img src="https://velog.velcdn.com/images/a700hui/post/43313437-dfa1-4c10-9302-06769cbf09ee/image.png" width="60%" />
버전 확인 후 Git을 사용하기 위해 <span style="background-color: yellow;">사용자 정보(name, email) 설정</span>해야 한다. 만약 사용자 정보를 제대로 셋팅해주지 않으면 커밋내역에서 계정 이름이 아닌 유저이름이 올라갈 수 있다!!

<p><strong><code>git --global user.name &quot;이름&quot;</code></strong>
<strong><code>git --global user.email &quot;이메일&quot;</code></strong></p>
<img src="https://velog.velcdn.com/images/a700hui/post/6c0d890c-e8bc-43eb-b653-308dd8641fae/image.png" width="90%" />

<p>제대로 설정 되었는지 확인해보자!!</p>
<img src="https://velog.velcdn.com/images/a700hui/post/8e84bd53-35f1-410d-be7b-175ba49e0931/image.png" width="80%" />
설정 제대로 된거 같다. 혹시나 이름과 이메일을 실수로 잘 못 입력했으면 삭제하고 다시 입력하면 된다. 

<p><span style="background-color: yellow;">선택 삭제</span>
<strong><code>git config --global --unset user.name 이름</code></strong>
<strong><code>git config --global --unset user.email 이메일</code></strong>
<span style="background-color: yellow;">전체 삭제</span>
<strong><code>git config --global --unset-all user.name</code></strong>
<strong><code>git config --global --unset-all user.email</code></strong></p>
<p>마지막으로 삭제가 잘 되었는지 확인할 수 있고, 현재 사용자 정보가 어떻게 되는지 확인하는 명령어는 <strong><code>git config --global --list</code></strong>다. </p>
<p>기초 셋팅이 다 끝났다면 Git 다른 명령어 들을 알아보자!</p>
<hr />
<h3 id="git명령어_오늘-배운-것">Git명령어_오늘 배운 것</h3>
<h4 id="1-git-init---코드-관리를-시작하는-명령어">1. git init - 코드 관리를 시작하는 명령어</h4>
<p>init는 initialize의 준말이다. 초기화하다, <span style="background-color: yellow;">초기 세팅하다</span>의 뜻을 가지고 있다. 
프로젝트 시작 전 <span style="background-color: yellow;">딱 한 번만 입력</span>하면 된다. (여러 번 입력해도 문제되진 않음)
<span style="background-color: yellow;">정확한 프로젝트 폴더(경로)</span>에서 입력해야함.(잘목하면 데스크탑 전체 파일, 폴더가 다 기록됨)
아래는 우클리해서 바로 터미널(Git Bash)로 가는 법이다. </p>
<p><strong><code>맥 - 새로운 터미널 열기</code></strong></p>
<img src="https://velog.velcdn.com/images/a700hui/post/0e47bf7c-f840-4247-8649-fc87649ec7f8/image.png" width="40%" />

<p><strong><code>윈도우 - Open Git Bash here</code></strong></p>
<img src="https://velog.velcdn.com/images/a700hui/post/747eadf4-0d11-4e9c-a49f-8b36c72db012/image.png" width="50%" />

<p>git init명령어 준 뒤 <code>.git</code>이라는 파일이 생성 된었다. 이때부터 코드 변경을 git에서 추적한다. </p>
<img src="https://velog.velcdn.com/images/a700hui/post/a5988d5b-f376-4b00-9037-2eb871401268/image.png" width="100%" />
여기서 Gittest이외의 다른 폴더에서 git init 명령어를 입력하면 안된다. pwd로 현대 경로 확인 후 경로가 다르면 cd명령어로 이동 후 git init 명령어 실행한다. 

<h4 id="2-git-add--git-commit--m-메세지">2. git add &amp; git commit -m &quot;메세지&quot;</h4>
<p>코드를 저장하는 명령어는 두개다. 
첫번 째 <code>git add</code> 는 <strong>저장하기 전 저장할 파일을 지정</strong>하는 것이다. +추가+, 만약 지정해야하는 파일이 많으면 <code>git add .</code> <span style="background-color: yellow;">add뒤에 한 칸 띄고 .</span>을 찍어서 사용하면 된다.<br />두번 째 <code>git commit</code> 은 <strong>지정한 파일을 저장</strong>하는 것이다. 
여기서 git commit -m <span style="background-color: yellow;">&quot;이 부분은 내가 무슨 코드를 짰는지 자세하게 적는 것이 좋다.&quot;</span></p>
<img src="https://velog.velcdn.com/images/a700hui/post/ad3f4d3f-67f9-477a-824f-42b4c264fcfd/image.png" width="100%" />
완료~!

<h4 id="3-git-status---저장-여부를-확인하는-명령어">3. git status - 저장 여부를 확인하는 명령어</h4>
<p>어떤 파일이 변경됐는지, 어떤 파일이 add됐는지 등 <strong>변경 상태</strong>를 확인하는 명령어다. </p>
<img src="https://velog.velcdn.com/images/a700hui/post/75a892bf-bff2-470b-9239-40e65bd2aff4/image.png" width="100%" />

<h4 id="4-git-log---저장-내역을-확인하는-명령어">4. git log - 저장 내역을 확인하는 명령어</h4>
<p>커밋 메시지를 제대로 작성했으면 log에서 커밋 메시지를 보고 코드 변경점을 추측 가능하다. </p>
<img src="https://velog.velcdn.com/images/a700hui/post/5b6dbf67-a0ba-4379-ab70-86e6f4fa9915/image.png" width="100%" />