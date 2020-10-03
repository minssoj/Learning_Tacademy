# 01. Git 기초
* staged 개념

---
# 02. GitHub 실습 I - Init, Add, Commit, Push, Diff, Status, Log
## Init
* Description 기록해주는 것이 좋음
* 연습용은 Private가 좋음
* 원격 서버에 폴더가 하나 만들어진 것
* ```git init``` : 컴퓨터에서 시작, master에 기록, .git (숨긴파일로)
* ```git config --global user.name (or user.email)```
* ```.gitignore``` ex: *.txt
* ```README.md``` : 페이지 사용방법, 라이센스 등을 기록
  * 프로젝트 내용 (이미지/로고), 설치방법, 코드예제, 개발 환경 설정 방법
  * 기여방법, 로그 변경, 크레딧 (오타 등의 수정 감사), 라이센스, 연락처


## Add
* ```git add [file]``` : stage에 올린다.
* ```git add .``` : 폴더의 모든 파일을 반영하겠다.

## Commit
* ```git commit -m "msg"```

##Log
* ```git log``` : 이전 commit 기록 살펴보기
  * sourcetree는 명령어 없이 log를 볼 수 있음
* ```git remote add orgin [url]``` : origin이라는 이름으로 [url]과 연결
  * 원결 repo와 내 repo 연결
* ```HEAD``` : 현재 상태
* ```git checkout``` : 7자리 주소 입력한 상태로 변경 (버전이동)
  * ```git log --all``` : checkout 전의 상태에는 (master)라 기록
  * ```git checkout ``` : 이전으로 돌아옴

## Push
* ```git push origin master``` : 동기화

## Status
* 현재 브랜치
* commit 목록
* commit할 변경 사항

---
# 03. GitHub 실습 II - Pull, Fetch, Reset, Revert, Stash, Fork, Push
---
# 04. Github Page 활용하기
