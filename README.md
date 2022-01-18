# GIT TOY


## Git 그래프를 깔끔하게 정리 하기

### rebase : 지저분한 커밋 하나로 합쳐서 처리
- ex) 3개의 커밋을 하나의 커밋으로 합치고 싶을 경우
1. reabase -i head~3
2. 기준이 되는 커밋만 pick 하고 나머지 커밋들 s (squash) 처리 후 저장
3. 쓸데없는 커밋 메시지 제거 및 메시지 변경
4. 이미 push 해왔다면 force push 해서 원격지랑 로컬이랑 sink 맞춰주기
