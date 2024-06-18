<p><img alt="" src="https://velog.velcdn.com/images/a700hui/post/58d28bf2-3c53-464d-97eb-6470f7c57ef1/image.png" /></p>
<p>소프트웨어를 개발하다 보면 클래스도 많고, .kt파일도 많다. </p>
<p>→ 파일이 많아지면 관리가 불편, 배포가 힘듦 </p>
<p>→ <strong>특정 기준을 세워 파일을 폴더 별로 나누어 관리</strong>하면 파일 관리가 용이해짐. </p>
<p>→ 그것을 <strong>패키지</strong>라고 함. </p>
<img src="https://velog.velcdn.com/images/a700hui/post/306579a8-7282-45b9-93d2-d0d2d0823531/image.png" width="30%" />

<hr />
<h3 id="패키지-사용"><strong>패키지 사용</strong></h3>
<p>패키지 내에 있는 파일들은 <strong>상단에 패키지를 명시</strong>해야 함.</p>
<img src="https://velog.velcdn.com/images/a700hui/post/3ed6c3cb-f5b1-4a25-acc8-c4ca46c94a7e/image.png" width="40%" />

<p>패키지 내에 있는 클래스 등을 사용할 때는 반드시 <strong>패키지명을 명시</strong>해야 함.</p>
<img src="https://velog.velcdn.com/images/a700hui/post/d34c6827-60d6-4be6-b3db-d82859ed9f6a/image.png" width="100%" />


<hr />
<h3 id="import">import</h3>
<p>패키지를 명시하면 코드 내에서 패키지 명을 생략할 수 있다.</p>
<img src="https://velog.velcdn.com/images/a700hui/post/32dfb2b2-007a-4e7e-9daf-caa76b1c6742/image.png" width="40%" />


<blockquote>
<p>👀 *<em>import *</em></p>
<p>패키지 명 뒤에 클래스 명 대신
→ package1에 있는 모든 클래스들 호출 가능</p>
</blockquote>
<img src="https://velog.velcdn.com/images/a700hui/post/71be4811-ff8f-4e8d-98f2-f70fff75388f/image.png" width="20%" />
<img src="https://velog.velcdn.com/images/a700hui/post/83d58d24-9716-4bd1-9c7a-905d7aa49731/image.png" width="40%" />


<p>👀 이름 충돌 as</p>
<p>로컬에서 충돌한 엔티티의 이름을 변경하여 충돌을 없앨 수 있음. </p>
<img src="https://velog.velcdn.com/images/a700hui/post/293ddecd-3553-4771-a676-e079a01aba7b/image.png" width="60%" />