## github-강의필기


### 1강. git 설치 및 사용법 익히기

cmder 사용

git —version : git 의 버전을 확인

git config — list : 모든 설정들을 확인할 수 있음.  q : 나가기

git config —global -e

code .  : 현재 디렉토리가 visual studio 로 열림.

git : git 명령어 사용법에 대해서 출력

git config —global user.name euni00

git config —global user.email euneee2000@naver.com : git 환경설정

git clone https://github~~ : 저장소에 있던 파일들이 내 컴퓨터로 clone

git add document.txt : txt파일 추가

git commit -m “Add Text file [document.txt]” 

git push : 원격 저장소(git)에 실제로 적용함.



### 2강. 오픈소스의 개요 및 오픈소스 활동을 하는 이유

commiter(커미터) : 특정한 프로젝트를 오픈 소스로 만들어서 관리하는 사람들을 의미함.

오픈소스 라이센스 : MIT License, Apache License, GPL, Beerware



### 3강. Git이 등장한 배경과 git의 장점

소스코드를 여러 명이 동시에 보면서, 소스코드를 수정해야 하는데 이러한 작업을 git과 같은 협업 관리 도구를 사용한다. & 포트폴리오 관리에 용이.

분산적인 개발 : 전체 개발 내역을 각 개발자의 로컬 컴퓨터로 복사할 수 있음.

효율적인 개발 : 변경된 내용만 처리, 메모리적인 효율성 뛰어남

비선형적인 개발 : 프로젝트의 가지치기가 가능, 트리구조

변경 이력 보장 : 별도의 영역에서 관리, 안전하게 프로젝트 운영



### 4강. Git의 동작 원리

깃 프로젝트에 담겨 있는 데이터들은 파일 시스템 상에서의 스냅샷(snapshot)

실제로 프로젝트를 커밋(Commit)하여 적용할 때의 순간을 중요시한다는 특징.

파일자체를 저장하기보다 수정 내역 자체를 저장함.



### Git 프로젝트의 세 가지 구성 요소

-Working Directory : 작업할 파일이 있는 디렉토리

-Staging Area : Commit을 수행할 파일들이 올라가는 영역

-Git Directory : Git 프로젝트의 메타 데이터와 데이터 정보가 저장되는 디렉토리### 12강. git archive 명령으로 소스코드만 압축하기

저장소 : 실제 소스코드가 담겨있으면서 커밋 내역 등의 모든 작업 이력이 담겨 있는 공간 



### 5강. 소스코드 수정하여 git 저장소에 반영하기

dir : 존재하는 디렉토리 보기

git status : 특정한 파일이 추가되었음을 표시

git my_module.py : 실제로 staging area 에 넣음. -> 실제로 commit할 수 있게 함.

git reset my_module.py : staging area로 부터 다시 내리고 싶을 때.

git add . : git 프로젝트를 기준으로 해서 모든 수정된 내역들이 알아서 반영

git commit -m “Add my_module [Add]” : my_module 파일을 만들고 Add 함수를 만들었다고 메세지를 넣어서 commit

git push : 실제로 git에 반영  

### 6강. Git commit 내역 수정하기

git checkout — module.txt : 저장하기 전으로 파일 원상 복구

git commit —amend : commit 메세지를 수정할 수 있음.

git log : 반영된 내역들을 확인해볼 수 있음

git reset —hard 90d40~~~ : 해당 commit 위치로 돌아가고 그 이후의 commit은 삭제한다.

git push -f : 강제로 push



### 7강. Git branch의 개요 및 사용해 보기

브랜치(branch) : 동시에 여러 개발자들이 프로젝트에서 각기 다른 기능을 개발할 수 있음.

마스터 브랜치 -> 배포용으로 사용, 안정화가 되어있는 프로젝트 

합치기(Merge)가 수행되기 전까지는 안정적으로 배포가 이루어짐. 

git branch : 현재 존재하는 branch를 보여줌

git branch develop : develop branch를 추가 

git checkout develop : 다른 branch로 접속하고자 할 때 , develop branch로 접속

git checkout master : master branch로 접속함.

git merge develop : develop branch를 master branch와 합

git branch -d develop : develop branch의 역할을 다했기 때문에 



### 8강. branch 충돌(conflict) 처리하기

### 9강. git 원격 저장소(remote repository) 관리하기

git remote : 현재 원격저장소로 어떤 것이 등록되어 있는지 확인

git remote show orgin : 특정한 원격저장소에 정보를 자세히 확인하고 싶을 경우

git remote add test (repository github 주소) : 특정 원격저장소를 등록하고 싶을 때

git remote -v : 전체목록 확인

git remote rename (기존 이름) (바꾸고 싶은 이름) :원격저장소를 지칭하는 이름을 바꾸고 싶을 때

git log orgin/master : 다양한 git 명령어를 특정한 원격저장소에 대해서 수행할 수 있다.

git merge orgin/master

git remote rm temp : 특정저장소를 제거할 수 있다.



### 10강. Git log 다루기 

git log —stat : 각 commit에 대한 통계정보를 출력함.

git log —graph : branch와 병합정보를 그래프 형태로 출력함.

git log —p -3 : commit에 적용된 구체적인 항목들을 출력함.

git log —pretty=oneline : commit정보(한줄로)를 지정한 형식으로 출력함.

git log —pretty=format:”%h -> %an, %ar : %s” —graph : 특정 format을 정해줄 수 있음 + graph까지 사용 -> 86b9ab7 ->euni00, 45 minutes ago : Add my_module [Div] & comment



### 11강. git에서 소개글(README.md) 파일 작성하기

git pull : git에 있는 파일을 컴퓨터로

README.md -> md : markdown 확장자



### 12강. Git archive 명령으로 소스코드만 압축하기

git rebase -i (특정 commit) : 넣어준 commit의 위쪽으로 모든 commit을 확인

pick -> drop ff5f581 Drop Example 1.txt (pick  <commit> = remove commit)

git archieve --format=zip master -o Master.zip : ??

git archieve --format=zip master -o ../Master.zip : 상위 폴더에 해당 압축파일을 내보내고 싶을 때

### 13강. Git Rebase 명령으로 특정한 커밋을 수정/삭제하기
  
git init : git 프로젝트 초기화

Delete Example 1.txt를 수정하는 예제
git rebase -i HEAD~3(head를 기준으로 최근 3개까지 commit만 확인) : 메세지를 수정 

pick-> reword Delete Example 1.txt -> :wq -> Delete Example 1.txt -> Drop Example 1.txt

git rebase -i(특정 commit) : 넣어준 commit의 위쪽으로 모든 commit을 확인

pick -> drop ff5f581 Drop Example 1.txt(pick <commit> = remove commit)
  
### 14강. Git Config 환경 설정에 대해 알아보기
git config --list : 현재 git에 환경 설정이 어떻게 되어있는지
  
git config --global user.name "test" : 사용자 이름 설정
  
git config --global user.email "test@test.com" : 사용자 이메일 설정
  
ls -al : 모든 파일 출력
  
cat .gitconfig : gitconfig 파일의 내용 출력
  
vim .gitconfig : 파일 수정할 수 있음
  
git config --global core.editor vi : 기본 에디터를 vi로 
  
mkdir "Git Example" : "Git Example" 디렉토리 생성

ls
  
git init
  
### 15강. git commit의 날짜 변경 및 커미터(Commiter) 변경하기
1) rebase
touch "Example 1.txt" : 파일 생성
  
pick -> edit Add Exmaple 2.txt : edit = use commit, but stop for amending
  
GIT_COMMITER_DATE="Oct 1 10:00:00 2018 +0000" git commit --amend -no-edit --date ""Oct 1 10:00:00 2018 +0000"

git rebase --continue : 변경된 내용을 반영
  
2) flitering
  
git filter-branch -f --env-fliter \
  
> 'if [ $GIT_COMMIT = 98f6c1f7556ebd768ccd1190cc8d71fb3922a63f ]
  
  then
  
    export GIT_AUTOR_DATE="Mon Oct 1 10:00:00 2018 +0000"
  
    exprot GIT_COMMITER_DATE="Mon Oct 1 10:00:00 2018 +0000"
  
  fi'
  
3) commit 사용자를 바꾸는 방법
  
  git filter-branch -f --env-filter '
  
  OLD_EMAIL="test2@test.com"
  
  CORRECT_NAME="euneee2000"
  
  CORRECT_EMAIL="euneee2000@naver.com"
  
  if [ $GIT_COMMITER_EMAIL = $OLD_EMAIL ]
  
  then
  
    export GIT_COMMITER_NAME="$CORRECT_NAME"
  
    export GIT_COMMITER_EMAIL="$CORRECT_EMAIL"
  
  fi
  
  if [ $GIT_AUTHOR_EMAIL = $OLD_EMAIL ]
  
  then
  
    export GIT_AUTHOR_NAME ="$CORRECT_NAME"
  
    export GIT_AUTH0R_EMAIL ="$CORRECT_EMAIL"
  
  fi'
  

