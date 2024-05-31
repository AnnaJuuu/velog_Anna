<h3 id="github란">GitHub란?</h3>
<p>GitHub는 소프트웨어 개발자들 사이에서 가장 인기 있는 형상 관리(변경 사항을 추적, 제어하는 과정) 플랫폼 중 하나다. Git시스템을 기반으로 하며, 소스코드와 관련 파일을 저장하고 관리할 수 있는 웹 기반 호스팅 서비스를 제공한다. 깃허브의 주요 특징으로 버전관리, 협업, 이슈 트래킹, 웹 호스팅, 오픈소스 등이 있다. </p>
<h3 id="github세팅">GitHub세팅</h3>
<p><a href="https://github.com/"><strong>GitHub페이지</strong></a>로 들어가 회원가입하기, 메일 인증까지 해야 한다. 
<a href="https://usingu.co.kr/frontend/git/github%EC%97%90-repository%EC%A0%80%EC%9E%A5%EC%86%8C-%EB%A7%8C%EB%93%A4%EA%B8%B0/"><strong>Github에 Repository(저장소) 만들기</strong></a> &lt; 사이트 참고하시면서 저장소까지 마무리하기!</p>
<h3 id="git-remote-add-origin-깃허브-레포지토리-링크">git remote add origin 깃허브 레포지토리 링크</h3>
<p>내 코드를 GitHub repository에 연결하기!
<strong><code>git remote -v</code></strong> 는 레포지토리(저장소) 연동여부 확인할 수 있다.</p>
<img src="https://velog.velcdn.com/images/a700hui/post/534069e9-264f-4ae5-873a-ef51efc904dd/image.png" width="100%" />

<p>여기서 만약 주소 변경된 상황이면 <strong><code>git remote set-url 새로운 주소</code></strong> 명령어를 사용하여 저장소 url을 변경할 수 있다. </p>
<p>완전히 비어져 있는 레포지토리 경우에는 아래 코드를 복사에서 터미널에 넣어두면 자동으로 알어서 올라간다!</p>
<img src="https://velog.velcdn.com/images/a700hui/post/f1d0ec3e-d6e2-4cf7-8b1b-e5b7a7d38b1a/image.png" width="100%" />