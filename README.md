## github-강의필기

### 12강. git archive 명령으로 소스코드만 압축하기
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
  

