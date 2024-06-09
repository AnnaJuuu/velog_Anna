<h3 id="컴퓨터-구조를-알아야-하는-이유">컴퓨터 구조를 알아야 하는 이유</h3>
<p>처음으로 프로그래밍 공부를 시작하게 되면 대부분은 프로그래밍 언어의 문법부터 시작한다. 왜냐하면 보통 개발자는 코드만 잘 짜면 된다고 생각하기 때문이다. 나도 처음에 공부 시작할 때 문법부터 배우면 된다고 생각했었다. 하지만 이영상 저영상 찾아보다가 AI에 빠져서 AI로 첫 공부 시작했었다... </p>
<p>다시 본론으로 돌아와서 물론 프로그래밍 언어의 문법을 아는것도 중요하지만 그만큼 중요한게 컴퓨터의 동작원리다. 즉, 컴퓨터의 근간을 알아야 한다! 여기서 컴퓨터 근간이란 컴퓨터 구조와 운영체제라는 것이다. </p>
<hr />
<h3 id="컴퓨터-구조">컴퓨터 구조</h3>
<h4 id="1-컴퓨터가-이해하는-정보는-데이터와-명령어다">1. 컴퓨터가 이해하는 정보는 <strong>데이터</strong>와 <strong>명령어</strong>다.</h4>
<p>예) &quot;안녕하세요&quot;를 출력해라
여기서 <strong>안녕하세요</strong>는 데이터고, <strong>출력해라</strong>는 명령어다. </p>
<h4 id="2-컴퓨터의-4가지-핵심-부품은-cpu-메모리ram-보조기억장치-입출력장치다">2. 컴퓨터의 4가지 핵심 부품은 <strong>CPU</strong>, <strong>메모리(RAM)</strong>, <strong>보조기억장치</strong>, <strong>입출력장치</strong>다.</h4>
<img src="https://velog.velcdn.com/images/a700hui/post/0e789d58-f45c-4738-9b40-596316fc9a99/image.png" width="70%" />

<p><strong>1) CPU</strong> - 메모리에 저장된 명령어를 읽어들이고, 해석하고, 실행하는 장치다
CPU 내부 구성안에 살펴보면 ALU, 레지스터, 제어장치가 있다. 
ALU : 계산기 (계산을 위해 존재하는 회로들의 모음, 산소논리연산장치의 줄임말)
레지스터 : CPU내부의 작은 저장장치
제어장치 : <strong>제어 신호</strong>를 내보내고, 명령어를 해석하는 장치</p>
<pre><code>예) 120과 100을 더해라 
1. 제어장치는 `더해라` 라는 명령어와 `120, 100`이라는 데이터를 읽어들이고 임시 저장소인 레지스터에 저장한다. 
2. ALU는 레지스터에 저장된 데이터를 계산하고 계산된 값을 레지스터에 다시 저장한다. 
3. 결과값은 시스템 버스를 통해 다시 메모리에 저장된다. </code></pre><p><strong>2) 메모리(RAM)</strong> - <strong>현재 실행되는</strong> 명령어와 데이터를 저장하는 부품이다.
프로그램이 실행이 되려면 메모리에 저장되엉 있어야 한다. 
메모리 저장된 값의 위치는 주소로 알고 있다. (아래 사진에 오른쪽에 있는 번지가 주소다.)</p>
<img src="https://velog.velcdn.com/images/a700hui/post/ab152e49-56df-4cbb-ac57-a1a7809f70e4/image.png" width="40%" />

<p><strong>3) 보조기억 장치 - 전원이 꺼져도 보관될 프로그램을 저장하는 부품</strong></p>
<ol>
<li>용량은 RAM에 비해 크다.</li>
<li>RAM에 비해 가격이 저렴하다.</li>
</ol>
<p><strong>4) 입출력장치 - 컴퓨터 외부에 연결되서 컴퓨터 내부와 정보를 교환할 수 있는 부품</strong></p>
<hr />
<h3 id="4가지-핵심-부품을-연결해주-것">4가지 핵심 부품을 연결해주 것</h3>
<p><strong>1. 메인보드(마더보드) - 컴퓨터의 부품들을 연결 시켜주는 판</strong></p>
<p><strong>2. 시스템 버스 - 정보를 주고 받을 수 있는 통로</strong>
주소 버스 : 주소를 주고 받는 통로
데이터 버스 : 명령어와 데이터를 주고 받는 통로
제어 버스 : 제어신호를 주고 받는 통로</p>
<p><strong><code>메모리 읽기</code></strong>
<img src="https://velog.velcdn.com/images/a700hui/post/5495f6e8-0d28-4af6-81bd-918dea014aa0/image.png" width="70%" />
<strong><code>메모리 쓰기</code></strong>
<img src="https://velog.velcdn.com/images/a700hui/post/2109ee23-0262-4ddb-8a45-a077973fa81a/image.png" width="70%" /></p>
<p><a href="https://www.youtube.com/watch?v=LBqJwmFMQHI">강의 영상</a></p>