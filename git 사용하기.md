# git 사용하기
버전관리와 협업을 잘하기 위해서는 깃의 활용이 필수적이다. 
열심히 공부해서 훌륭한 사람이 되자

## 1.git 이란?
깃(Git /ɡɪt/[5])은 컴퓨터 파일의 변경사항을 추적하고 여러 명의 사용자들 간에 해당 파일들의 작업을 조율하기 위한 분산 버전 관리 시스템이다.
> 간단하게 과제를 할때 최종버전 -> 진짜최종버전 -> 찐찐최종 이런식의 버전관리를 도와줌  
> 그리고 이것을 github라는 서버에 올려서 남들과 편리하게 공유할 수 있음


[Git 홈페이지](https://git-scm.com/downloads)  
[나무위키-git](https://namu.wiki/w/Git)  
[위키백과-git](https://ko.wikipedia.org/wiki/%EA%B9%83_(%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4))  

## 2.git 사용하기

### 1.git 설치하기
먼저 본인의 컴퓨터에 git이 설치되어있는지 확인해보자
#### window의 경우
![image](https://user-images.githubusercontent.com/76804251/131245797-fe512e86-37b5-469f-9f7f-d2a59c8f772c.png)

> 우선 윈도우 검색창에 git bash 라고 쳤을때 있으면 깃이 설치되어 있는것이다. git bash를 실행시키고 다음단계로 넘어가자.

[git 홈페이지](https://git-scm.com/downloads)에 들어가서 자신의 운영체제에 맞는 것을 다운받자.


![image](https://user-images.githubusercontent.com/76804251/131245907-3635814a-c491-425f-9792-1a79fa5007bb.png)


#### 라즈베리파이의 경우
우선 터미널에 들어가서 깃이 설치되었는지 확인해본다. 다음의 명령어를 쳐본다.
```
git --version
```
이때 git의 버전이 뜨면 설치되어있는것이고 뜨지 않는다면 설치를 해야한다. 
```
sudo apt-get install git
```
다시 버전을 확인해 깃이 설치된것을 보고 다음단계로 넘어가자.

 

### 2.git 환경설정하기
 - 유저 이름설정
 ```
 git config --global user.name "your name"
 ```
 ![image](https://user-images.githubusercontent.com/76804251/131278593-30579893-3c97-46fe-ae83-8390f3e8c030.png)

  - 유저 아이디 설정
 ```
 git config --global user.email "your email"
 ```
 ![image](https://user-images.githubusercontent.com/76804251/131278653-f9782604-762f-4213-8db6-aaa6ea1ef5d6.png)

 > git에 가입한 이메일로 설정 해야됨
 
 설정한것 확인하기
 ```
 git config --list
 
 ```
 ![image](https://user-images.githubusercontent.com/76804251/131278707-658de641-7a1f-49a4-b93a-3cea3e531e26.png)
> 밑쪽을 보면 설정한 유저이름과 아이디를 확인할 수 있다.

### 3. 레포지터리 만들기

#### git의 전체공간을 간단하게 하면 3가지의 공간으로 나눌수 있다.

|**working directory**|**staging area**|**.git directory**|
|------|---|---|
|파일 작업공간|저장준비|버전저장소| 

**working directory**에서는 말 그대로 파일들을 제작하고 생성하는곳을 말한다.  
**staging area**는 뒤에 나오는 커밋하고 싶은 파일들을 스테이징 하는공간이다.  
**.git directory**는 원하는 버전을 커밋하는 곳이다. 한마디로 최종 최최종 최최최종 파일들을 저장하고 관리하는공간.   
> 지금은 간단게하 알기만 하고 추후 배워가면서 이해해보도록 하자 

#### git 초기화
먼저 내 컴퓨터에 버전을 관리할 저장소를 만들어야한다. 앞에서 실행한 git bash에 원하는 곳으로 이동하여 다음의 명령어를 입력해보자
```
git init 
```
![image](https://user-images.githubusercontent.com/76804251/131280749-ab013525-873a-4861-baff-f75c3f413d3f.png)

아무일도 안일어 난거 같지만 저장소가 만들어져있다. 확인하는 방법은 다음과 같다.
```
ls -al
```
그러면 .git 이라는 파일이 생긴것을 확인할 수 있다.
![image](https://user-images.githubusercontent.com/76804251/131280777-65bb40fa-658a-4d40-98fe-5f9a3a1787a2.png)

#### 추가파일 올리기
저장소에 저장하고 싶은 파일을 **staging area**에미리 올려놓는다.
```
git add .
```
> 여기서 . 은 모든 파일을 선택할떄 쓰는것. 원하는 파일이 있으면 . 대신 파일명을 쓸것
다음의 명령어로 상태를 확인 할수 있다.
```
git status
```
![image](https://user-images.githubusercontent.com/76804251/131280876-f3d0130e-449b-4fee-9ccd-98c3b78f3ee9.png)
> 여기서는 1.txt 파일이 추가되어 올라가 있는것을 볼 수 있다.

올리고싶은 파일이 올라간것을 확인했으면 커밋으로 히스토리를 만들어 준다.
```
git commit -m "first commit"
```
> ""사이에는 원하는 코멘트를 써주면 된다.
이렇게 하면 **.git directory**에 자신의 파일이 저장된것이다.

### 4. 깃허브와 연동하기
내가 저장해놓은 파일들을 다른사람들과 공유하고 싶으면 깃허블르 이용하면 된다.  
우선 [깃허브]()에들어가 회원가입을 한다음 새로운 레포지터리를 만든다.
