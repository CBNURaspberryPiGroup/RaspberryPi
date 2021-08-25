# 라즈베리파이 사용하기

## 라즈베리파이란?
![image](https://user-images.githubusercontent.com/76804251/130781260-52b600cd-d1d4-40b6-84c7-03aca8f1294a.png)

> 라즈베리 파이(영어: Raspberry Pi)는 영국 잉글랜드의 라즈베리 파이 재단이 학교와 개발도상국에서 기초 컴퓨터 과학의 교육을 증진시키기 위해 개발한 신용카드 크기의 싱글 보드 컴퓨터이다

[라즈베리파이 나무위키](https://ko.wikipedia.org/wiki/%EB%9D%BC%EC%A6%88%EB%B2%A0%EB%A6%AC_%ED%8C%8C%EC%9D%B4)  
[라즈베리파이 위키백과](https://namu.wiki/w/%EB%9D%BC%EC%A6%88%EB%B2%A0%EB%A6%AC%20%ED%8C%8C%EC%9D%B4(%EC%BB%B4%ED%93%A8%ED%84%B0))

## 라즈베리파이 설치해보기
### 1.라즈베리파이 os 다운로드

![image](https://user-images.githubusercontent.com/76804251/130781350-8b6a9ac1-931e-49d6-b85d-c1bc4603005a.png)

> 검색창에 '[raspberry pi imager](https://www.raspberrypi.org/software/)' 사이트에 들어가서 본인 운영체제에맞는 것을 다운로드 합니다.  
> sd카드 리더기를 이용하여 sd카드를 컴퓨터에 연결합니다.



![image](https://user-images.githubusercontent.com/76804251/130782621-24c9d49b-f950-4689-93ec-583e0afabaf6.png)
> storage에서 sd카드를 선택하고 operating system에서 설치할 라즈비안os 버전을 선택한다. (가장위에것을 추천)  
> 시간이 조금걸린다.

- 모니터와 키보드가 있을경우 **2.라즈베리파이연결하기** 보기
- 모티어와 키보드가 없을경우 **3.원격으로 라즈베리파이연결하기** 보기

### 2.라즈베리파이연결하기
> os설치가 끝난 sd카드와 모니터 노트북을 라즈베리파이 본채와 연결한후 작동시킨다.
>  부팅이 되면 아이디와 비밀번호를 물어보는데 초기의 라즈베리파이 아이디와 비밀번호는 다음과같다.  
```
ID: pi  
Password: raspberry  
```
- Password를 입력할때는 치는게 안보이고 커서가 안움직이는데 정상이다. 그냥 치면된다.

### 3.원격으로 라즈베리파이연결하기
> 모니터가 없다면 라즈베이파이를 sd카드와 연결해서 부팅해도 상태를 알 수 가 없다.  이때는 컴퓨터에 원격으로 접속하여 제어해야한다.

![그림1](https://user-images.githubusercontent.com/76804251/130786560-e21b0570-6c76-4680-ab17-ab031395029c.png)


> sd카드를 다시 컴퓨터와 연결하여 boot에 들어가 다음과 같이 2개의 파일을 만든다. (새로만들기 > 택스트파일 > 이름바꾸기)
- 이떄 파일명은 확장자까지 포함해야한다


```
- ssh  
- wpa_supplicant.conf
```   
> ssh 파일은 이름만 있고 내용은 없지만, wpa_supplicant.conf 파일은 파일명을 바꾸기전에 아래의 내용을 넣어야한다.


```
country=US ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev 
update_config=1 
network={
 ssid="WIFI 이름" 
psk="WIFI 비밀번호" 
scan_ssid=1 
}
```
> 위의 사진처럼 완료되었으면 sd카드를 분리하고 라즈베리파이와 연결하면된다.

#### putty 다운받기
> 라즈베리파이와 컴퓨터의 원격연결을 통해 제어할려면 [putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
