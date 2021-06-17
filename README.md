## github-강의필기

### 12강. git archive 명령으로 소스코드만 압축하기
git archieve --format=zip master -o Master.zip : ??
git archieve --format=zip master -o ../Master.zip : 상위 폴더에 해당 압축파일을 내보내고 싶을 때

### 13강. Git Rebase 명령으로 특정한 커밋을 수정/삭제하기
git init : git 프로젝트 초기화

Delete Example 1.txt를 수정하는 예제
git rebase -i HEAD~3(head를 기준으로 최근 3개까지 commit만 확인) : 메세지를 수정 
pick-> reword Delete Example 1.txt -> :wq -> Delete Example 1.txt -> Drop Example 1.txt
