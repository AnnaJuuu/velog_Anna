<p>git pull과 git fetch는 둘 다 git에서 원격 저장소의 업데이트를 가져오는 명령어다. 하지만 두 명령어는 목적과 등장 방싱에서 차이가 있다. </p>
<h3 id="git-pull">git pull</h3>
<p>원격 저장소의 업데이트를 가져오는 동시에 현재 작업하는 로컬 브랜치로 병합한다. 즉, <strong><code>git pull = git fetch + git merge.</code></strong></p>
<h3 id="git-fetch">git fetch</h3>
<p>원격 저장소의 업데이트를 확인하고 로컬 저장소에 업데이트된 내용을 이름없는 임시 브랜치로 다운로드한다. 하지만 이 내용을 현재 작업 중인 브랜치에 병합하지 않는다. 
즉,<code>git fetch</code>를 실행한 후 <code>git merge</code>를 사용하여 로컬 복사본과 변경 내용을 수동으로 병합해야 한다.</p>
<h3 id="차이점">차이점</h3>
<p>fetch과 pull의 차이점은 병합하기 전에 변경 내용을 검통할 수 있으므로 일반적으로 pull보다 fetch가 더 안전하다. 또한 fetch는 병합을 수행하지 않고 변경 내용만 다운로드하기 때문에 더 빠르다. </p>
<p><a href="https://velog.io/@msung99/push-%EB%B8%8C%EB%9E%9C%EC%B9%98-%EA%B9%83%ED%94%8C%EB%A1%9C%EC%9A%B0-pull"><strong>fetch 와 Pull 의 차이점/병합과정 참고사이트</strong></a></p>
<p>[<strong>pull, fetch의 사용법</strong>] (<a href="https://chaeyoung2.tistory.com/43">https://chaeyoung2.tistory.com/43</a>)</p>