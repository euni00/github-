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



