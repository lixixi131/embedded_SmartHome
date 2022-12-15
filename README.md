# Embedded_SmartHome
## 스마트 홈을 위한 라즈베리 파이 기반 프로그램

----
## 개발 목적
임베디드 시스템(라즈베리 파이)를 활용하여 스마트 홈을 제작하고 집의 기기들을 제어하는 것을 목표로 한다.   
추가로 단순 제어뿐만이 아닌, 여가시간 중 즐길 수 있는 게임도 탑재한다.

----


## 전체 시스템 구조
<img src = "https://user-images.githubusercontent.com/46674066/207770377-415019a8-d35f-4e05-a736-fc1f1df2b1cd.png" width= "40%" height="40%">

전체 시스템은 라즈베리파이-알람 시스템-게임 시스템-가전 시스템으로 구성되어있다.   
스마트폰이 기기와의 UART 통신을 통해 기기들을 제어하는 과정은 다음과 같다.
1. 라즈베리파이와 스마트폰을 UART 통신으로 연결한다.
2. 스마트폰에서 라즈베리파이에게 데이터를 보낸다.
3. 라즈베리파이가 최초로 데이터를 받게되면 시스템이 가동되고, 스마트폰으로 사용 UI를 출력한다.
4. 스마트폰은 UI를 통해 사용할 기기의 번호를 보낸다. 
5. 스마트폰은 받은 번호를 통해 기기들의 사용여부를 결정한다.


----
## 개별 시스템 구조
----


## 제한 조건 및 구현 내용
<span style="color:yellow"> 노란 글씨입니다. </span>

### 시스템 기능 제어
블루투스 연결을 통한 시스템 기능 제어
### 알람
실시간 시간 계산, 알람 설정 시간 비교, BUZZER / LED 동작
### 게임
UP & DOWN 게임 실행, 스마트폰을 통한 정답 입력



## 개발 시 문제점 및 해결방안


|문제점|문제점 설명|
|:---:|:---:|
|집 상태 확인 기능|일상생활에 많이 사용할 수 있는 기능을 추가하고 싶었음<br> 기능을 여러가지 사용하다보니 전기요금을 확인할 수 있는 기능을 추가 하면 좋지 않을까?| 

|해결법|해결법 설명|
|:---:|:---:|
|전기요금 공유변수 사용|기능별 <span style="color: red">가중치</span>를 적용하여 기능을 사용할 때 마다 요금이 가산되도록 함<br> 이때, 전기요금에 대한 공유변수를 사용하여 쓰레드간에 값을 공유할 수 있도록 함|
