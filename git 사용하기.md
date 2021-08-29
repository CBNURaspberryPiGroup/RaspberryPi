# git 사용하기
버전관리와 협업을 잘하기 위해서는 깃의 활용이 필수적이다. 
열심히 공부해서 훌륭한 사람이 되자
- 여기에서는 putty를 이용하여 라즈베리피이에 원격접속하여 깃을 이용하지만 다른곳에서도 똑같이 사용된다.
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

### 2. 레포지터리 만들기
