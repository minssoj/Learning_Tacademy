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
* ```git log --all --decorate --graph --oneline``` : CLI창에서 그래프로 보고 싶을 때

---
# 03. GitHub 실습 II - Pull, Fetch, Reset, Revert, Stash, Fork, Push
## Remote
* ```git remote add origin "url"``` : 원격 저장소에 연결 이름을 'origin'으로
* ```git remote -v``` : 연결된 것을 확인할 수 있다.

## Push
* ```git push -u origin master```

## Clone
* ```git clone [url]``` : 원격 저장소에서 저장

## Branch
* master의 경우 배포 버전이다.
* ```git branch [name]``` : 길을 만들어 따로 작업을 진행하겠다.
* ```git checkout [name]``` : 브랜치간 이동...name으로 이동
* ```git merge [name] ``` : name branch를 현재 branch로 합침
* 이 후에 합침
* ```git rebase master``` : base를 master로 re-base 한다 (기준점을 바꾼다)
* ```git branch -d [name]``` : 완료된 branch 삭제...version 관리가 힘들 수 있기에

## Config
* ```git config --global alias.adog "--all --decorate --graph --oneline"``` : 자주 사용하는 것 축약어로...

## Fetch
* ```git fetch``` : 원격 저장소 가져오기
* 협업할 때는, Pull보다는 Fetch를 (충돌 방지)

## Pull
* ```git pull``` : Fetch에 Merge까지

## 실수하는 경우
### reset
* ```gut reset [option] [branch]``` : Branch 이후 내용 지우자
* ```gut reset --hard [해시번호]``` : 저 상태로 돌아감
### Revert
* ```git revert [branch]``` : 수정한 기록도 남기자
### Stash
* ```git stash``` : 현재 작업하고 있는 작업물을 따로 저장하기

## Fork
* 내 로컬에 떠오기
* 명령어 없이, 사이트에서 가능

# Pull Request 하는 법
```Fork``` - ```Clone + Remote 설정``` - ```Branch 생성``` - ```add, commit, push``` - 
```Pull Request (PR) 생성 ``` - *Code Review* - *Merge PR* - ```Merge 이후 Branch 삭제 및 동기화```

---
# 04. Github Page 활용하기
## Markdown
* 연동 문제 때문에 블로그보다는 많이 사용
* ```vscode```에서 사용하려면 ```extend```tab에서 ```markdown preview enhanced```다운

### H태그 
* Header를 의미
* H5 (#5개)부터는 잘못된 사용

### 글씨체
* ```_``` : _Italic_
* ```**``` : **BOLD**
* ```**_``` : **_Italic+BOLD_**
* ```>``` 
    > 인용문

### list & table
* list 순서가 없는 경우 : ```-``` or ```*```
* list 순서가 있는 경우 : ```숫자.```

* 표의 경우 ```||||```으로 column 정하고 ```|---|----|-----|``` 후에 항목 채우기
* ```---``` : 경계선

### link & image
* link : ```[name](주소)```
* image : ```![name](이미지주소)```

### 코드 & 수식
* ` ` : 코드 한줄 (하이라이트)
* ``` 개발도구 이름 + code``` : 해당언어 문법에 맞게 해준다.
    * 코드 공유시 `carbon`사용
* `$`: 사이에 쓰면 수식, $를 두개를 쓰면 수식을 중앙에
    * `^` : 제곱, `_`
    * `tex` 에 검색하여 사용

### 다이어그램
* mermaid

## Blog
* ```TIL``` : Today I Learned, 오늘 배운것
* ```Jekyll Blog```
    * 블로그 관리는 CLI 추천 -  windows에서는 Ruby 필요 [다운로드링크](https://jekyllrb.com/docs/installation/windows/)

### 오늘의 블로깅
1. Thema Repo Clone & Fork
    * 인기 테마 : `Minimal mistake` git clone 하기
    * `.git`폴더 삭제하기
    * `git remote add origin 블로그 레포지토리 주소` 그 후에 push
    * 블로그 확인 : 계정이름.github.io
    
2. Jekyll 구조 살펴보기
    * `_config.yml` : 설정파일
    * `_posts` : 블로그 포스팅
    * `_pages` : 개별 페이지
    * `_includes` : 글에 포함되는 개별 요소
    * `_layouts` : 글의 양식
    * `assets` : image, css 등
    * `index.html` : 표지
    * `Liquid Tag`를 공부해야 블로그 활용할 수 있다. 

3. 기본 setting : ```_config.yml```
4. 첫 포스팅 연습
    * `_posts`에 `연도-월-일-아룸.md`파일 생성
5. About 페이지 작성

---
# 참고
* About Page (CV) = Portfolio Resume
    * https://sujinlee.me/professional-github/
    * https://woowabros.github.io/experience/2017/07/17/resume.html
    
* 강사님 페이지
    * https://youtube.com/c/수비니움의코딩일지
    * https://subinium.github.io
    * https://www.facebook.com/AI.Lookbook
    * https://www.facebook.com/algoguide/
    * https://www.facebook.com/shovelingdesignoper/


