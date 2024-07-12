ㅇ 파라미터 : AI에게 질문 시 필요 부가정보
  ex) 날씨 알려줘 X -> 오늘 광주 날씨 알려줘

ㅇ git bash 붙여넣기 하는법 : shift + insert

ㅇ 토큰 : 문장으로 치면 "단어"(뛰어쓰기 기준)

ㅇ prompt engineering : 질문하는 방법

ㅇ {} -> 파이썬에서는 dictionary(사전)

ㅇ markdown : 텍스트에 효과주기 가능함
- # -> 굵고 크게 / - -> ㆍ
- * / ** / ***
- 글 삭선 -> ~글자~
- --- -> 문단선
- 링크, 이미지 생성방법
링크 -> [이름](주소URL)
이미지 -> ![이미지](이미지 주소)

ㅇ GIT : 분산버전관리시스템
- 버전관리 : 언제 수정했고, 왜 수정했고 ex) google Docs

ㅇ 중앙 vs 분산
- 분산
1. 동시 다양한 작업가능
2. 중앙의존(X) -> 각 로컬에서 복구 가능
3. 인터넷 없이도 변경가능

★GIT의 영역★
1. Working directory : 실제 작업 중인 파일이 위치하는 영역'
2. Staging Area : Working directory에서 변경 된 파일 중.. 다음 버전에 포함시킬 파일들을 첨삭하는 중간 준비영역(가상의 공간)
3. Repository : 버전 이력과 파일들이 영구히 저장되는 영역 -> 모든 버전과 변경이력이 기록 된다.

ㅇ git commit 과정
1. touch 파일명
2. git add . 또는 .. 또는 파일명(. : 자식, .. : 부모)
3. git commit -m "message"

☆local 저장소가 바뀌었을 경우 취해야 할 행동 2가지☆
1. 윈도우 시작 -> 자격 증명 관리자 삭제(초기화)
2. 바탕화면 bash실행 -> git e-mail, name 바꾸기
- git config --global user.email "qwsxza019@naver.com"
- git config --global user.name "강건준"

ㅇ 바로 직전 생성한 commit 수정하기 -> local 저장소에서의 작업
1. git commit --amend 실행
2. Vim 에디터가 열림
3. a(입력모드) 누르고 아래창에 끼워넣기 나오는지 확인
4. 끼워넣기 나오면 내용 변경 가능
5. 변경 후 esc 후 `:wq` 입력 후 엔터

★★★★ 원격 저장소 <---> 로컬 저장소 이동방법

- 로컬 -> 원격 (init은 둘중 하나만)
1. Commit 완료된 상황
2. git remote add origin(별명) URL
3. git push origin(별명) master
4. 두번째 부터는 git push

- 원격 -> 로컬 (init은 둘중 하나만)
1. 원하는 곳에서 git bash 열기
2. git clone URL
3. 두번째부터는 git pull

ㅇ lab.ssafy 주의사항 : project URL 생성시 내 아이디로 생성 (그래야 내 소유가 됨)

ㅇ git ignore (인터넷에 git ignore 검색 후 파이썬이나 각 필요 항목마다 검색 사용)
- git ignore 생성 후 내용에 파일 이름 작성
- 만약 git ignore을 했음에도 선택 파일이 불빛이 들어오면 git이 작용하고 있다는 뜻
- 이런 경우 git rm --cached 명령어를 사용하여 git 캐시에서 삭제

ㅇ git revert&reset

- git revert <commit id>
  : 이전에 있던 커밋을 없던 일로 되돌린다는 "커밋"생성 -> 기록이 남음
    커밋을 만드는 것이기에 "message 작성 필요"
    - 공백을 사용해서 여러 commit을 한번에 실행 취소 가능
    - ..을 통해서 범위지정가능
    - --no-edit을 통해 편집기 사용 없엠 (Vim)
    - --no-commit을 통해 여러 커밋을 revert할 때 하나의 commit으로 묶을 수 있음


- git reset [옵션]
옵션 1. --soft : 삭제된 commit 기록을 staging area로 이동
    1. --mixed : 삭제된 commit 기록을 Working directory로 이동
    2. --hard : 삭제된 commit 기록을 저장 안함

- git reflog : HEAD가 이전에 가리켰던 모든 commit을 보여줌
              reset의 --hard 옵션을 통해 지워진 commit도 reflog로 조회하여 복구가능

- git undoing : 파일 내용을 수정 전으로 되돌리기
                (staging area -> W.D.로 이동)

- git restore : modified 상태의 파일 되돌리기
                (ctrl + Z의 역할)

- git rm --cached 파일명 : git 저장소에 commit이 없는 경우

- git restore --staged 파일명 : git 저장소에 commit이 있는 경우