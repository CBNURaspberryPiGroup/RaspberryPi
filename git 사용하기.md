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
![image](https://user-images.githubusercontent.com/76804251/131284919-b0ffa7f3-b401-48ab-ad7d-d28b9252f236.png)

> ""사이에는 원하는 코멘트를 써주면 된다.
이렇게 하면 **.git directory**에 자신의 파일이 저장된것이다.

### 4. 깃허브와 연동하기
내가 저장해놓은 파일들을 다른사람들과 공유하고 싶으면 깃허블르 이용하면 된다.  
우선 [깃허브]()에들어가 회원가입을 한다음 새로운 레포지터리를 만든다.
![image](https://user-images.githubusercontent.com/76804251/131284369-becbda57-bbd7-42ff-b255-01ecb2a08edc.png)
만들고나면 이런게 나오는데 이대로 따라하면 된다.
![image](https://user-images.githubusercontent.com/76804251/131284384-c8afee68-f9b7-422b-9697-e59ec502be48.png)
현제 우리는 커밋까지 완료된 상태이기때문에 내 깃허브와 연동만 하면된다.
```
git remote add origin https://github.com/wlans01/git.git
```
> 뒤에나오는 주소는 자신의 깃주소를 입력하자
다음의 명령어로 연결이 잘 되었는지 확인이 가능하다
```
git remote -v
```
![image](https://user-images.githubusercontent.com/76804251/131284782-1cf97c2b-523a-4cce-8efd-c5a0990367df.png)

만약 이전에 다른 주소로 연결되있어서 주소을 바꾸고 싶다면 주소를 지웠다가 다시 연결하면 된다.
```
git remote remove
git remote add origin https://github.com/wlans01/git.git(원하는 다른주소)
```

연결이 알맞게 된것을 확인했으면 푸쉬를 통해 서버에 올리면 된다
```
git push origin master
```

![image](https://user-images.githubusercontent.com/76804251/131284991-14e11a6f-64e5-4bb1-810f-26fbdba37f07.png)
> 뒤에 master은 브런치의 이름이다. 브런치 이름에 맞게 쓰면됨

깃허브 페이지로 와보면 내가 올린파일이 생성된것을 확인할 수 있다.

![image](https://user-images.githubusercontent.com/76804251/131285108-eec2a928-3735-4011-9422-ad1c529e1331.png)

### 5.계정인증하기
깃허브에 파일을올리기위해 주소와 연결하고 푸쉬를 하게되면 유저아이디와 인증토큰을 입력하라고 요구할떄가 있다.  
브라우저로 간편하게 인증이 가능하지만 그러지 못할경우 토큰을 생성해서 인증해야한다.

#### 인증토큰 생성하기
깃허브에 로그인해서 들어가면 오른쪽 상단에 setting을 찾아 들어간다.
![image](https://user-images.githubusercontent.com/76804251/131285265-34167ca3-c55d-4f08-ab2e-dd6f992d9f78.png)

메뉴들을 보면 중간 아래쯤에 developer settings

![image](https://user-images.githubusercontent.com/76804251/131285337-4bfa7b5a-d990-458c-98f7-d553f159e92d.png)

personal acess tokens 에서 새토큰을 생성한다.
> 이때 비밀번호 물어본다. 비번치면됨

![image](https://user-images.githubusercontent.com/76804251/131285408-b335b884-7763-4172-ba12-8850e517c540.png)

note 부분에 토큰 이름정하고
원하는 기능권한을 체크한다.
![image](https://user-images.githubusercontent.com/76804251/131285499-322f5d21-ef2a-4186-8555-1a3a6d8a6e5b.png)

> 풀 푸쉬 목적만 있다면 repo만 체크하면됨 아마도

이렇게 생성된 토큰을 이용하여 인증을 하면된다.  
name은 깃허브가입한 이메일  
password는 토큰을 입력하면됨

### 6.깃허브로 팀프로젝트 진행하기
앞으로 많이하게될 팀프로젝트는 대부분 깃허브를 통해서 할것이다 열심히 연습하자

#### 그룹으로부터 코드가져오기
처음 할 일은 그룹이나 팀의 github 주소를 에서 코드를 받아오는것이다.
```
git clone github주소
```
> 위의 명령어를 입력하면 팀에있는 코드를 전부 가져오게 된다.   
> 받아온 코드르 이용하여 각자가 담당한 부분을 수정하고 작업하면 된다.

필요한 작업이 끝나고 깃허브에 다시 공유하기위에 main 브런치에다가 push를 그대로 해버리면 큰일이난다.  
메인 브런치는 최종버전이기 때문에 그전에 확인을 하고 최종적으로 올리는 곳이다.
그러므로 새로운 브런치를 만들어서 push를 하자

```
git checkout -b 브렌치이름
```
![image](https://user-images.githubusercontent.com/76804251/131286532-5733dae0-cc9e-4cfa-a85d-8ff81942abc6.png)

> 브런치 이름이 master 에서 main으로 바뀐것을 확일 할 수 있다.
바뀐 브런치로 이전과 같이 저장하고 push 해주면된다.

```
git add .
git commit -m "first commit"
git push origin 브렌치이름
```
