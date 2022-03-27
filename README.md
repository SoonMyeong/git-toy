# GIT TOY


## Git 그래프를 깔끔하게 정리 하기

### rebase : 지저분한 커밋 하나로 합쳐서 처리
- ex) 3개의 커밋을 하나의 커밋으로 합치고 싶을 경우
1. reabase -i head~3
2. 기준이 되는 커밋만 pick 하고 나머지 커밋들 s (squash) 처리 후 저장
3. 쓸데없는 커밋 메시지 제거 및 메시지 변경
4. force push 해서 원격지랑 로컬이랑 sink 맞춰주기

---

### 체리픽 해보기

1. 아래와 같은 깃 그래프가 존재했을 때 master 브랜치에 feature#2의 특정 커밋만 붙이고 싶다면?
![img#1](https://user-images.githubusercontent.com/31875043/150362821-7f56e907-bd0e-4125-bcaa-413fad32c7ec.JPG)

2. 현재 master 브랜치 상황, 006파일을 추가한 feature#2 커밋을 끄집어 와보자  
![img#2](https://user-images.githubusercontent.com/31875043/150363416-77f9c131-4bfd-4f42-8ed6-46648a91b5cc.JPG)

3. $ git cherry-pick 4103a9f  
4. 띠용! 원하는 커밋을 꺼내서 master 브랜치에 006 파일이 생김!  
![img#3](https://user-images.githubusercontent.com/31875043/150364070-3c7a4662-975c-46c1-a72b-71a267a0dad6.JPG)

---

### 리베이스 해보기
1. feature#2 브랜치에 있는 3개의 커밋을 하나로 만들어 보자.  
![img#1](https://user-images.githubusercontent.com/31875043/150362821-7f56e907-bd0e-4125-bcaa-413fad32c7ec.JPG)  
2. git rebase -i head~3  
3. git-bash 에서 진행할 경우 아래 그림처럼 vim 이 열린다.  
![img#5](https://user-images.githubusercontent.com/31875043/150364767-94689d36-f947-42df-b2b8-b49215d30d14.JPG)  
4. 여기서! 하나를 픽한상태에서 나머지 두개의 커밋에 대해 squash 나 fixup을 해준다. (이번엔 squash로)  
(캡쳐가 안보인다..ㅠ 맨위에 커밋만 pick 으로 두고 나머지 2커밋을 s 로 바꿔준다.)  
5. 바꿔주면 또다시 vim 창이 열리며 커밋 메시지를 아래 그림처럼 수정할 수 있다. (남은 두 커밋에 대해선 메시지 주석처리)  
![img#6](https://user-images.githubusercontent.com/31875043/150365509-13ae1f97-b8e0-4f43-8d5a-1d2342c9452e.JPG)  
6. 띠용! 커밋메시지가 하나로 합쳐졌다.  
![img#7](https://user-images.githubusercontent.com/31875043/150365617-619a9f3c-6b0e-4df2-9919-19f582281b09.JPG)
7. 커밋메시지 합쳤으니까 master 브랜치에 merge 하여 master 브랜치를 최신화 시켜준다. (커멧 메시지 합치고서는 force push 해야 한다!!!!!)
(feature 브랜치가 어떤 일을 했는지 쉽게 알아볼 수 있게 되었다.)
![img#8](https://user-images.githubusercontent.com/31875043/150365922-e8ecb995-b408-4226-89a2-4e5e1a3cc3e1.JPG)

