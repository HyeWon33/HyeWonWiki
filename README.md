# HyeWonWiki

# 실수, 오류


---
목차  
[0. 미리 체크 ](##-0-선배님께-질문하기-전에-체크)  
[1. 오류 ](##1-오류)  
[2. 팁 ](#2-팁)  
[3. 터틀봇 작동 ](#3-터틀봇-ip연결-및-실행)  
---





## 0. 선배님께 질문하기 전에 체크

- .py 파일 실행권한 줬니?

- package 만들고 cm 했니?

- ros master uri, hostname 바꾸기 , source ~/.bashrc 했니?

- roscore 노드 켰니?

  rosrun 패키지이름 노드이름.py 이다잉

  roslaunch 는 런치파일 키는거다잉

- 터미널 껐다가 켜봤니?!!!!

- roscore가 실행이 안된다면 localhost자리에 아이피가 쓰여있으면 바꿔야지~!!!

## 1. 오류

### 1.1 turtlebot이 안 멈출때

- rosrun turtlebot3_teleop turtlebot3_teleop_key (단축말tele)

### 1.2 ssh: connect to host 192.168.0.34 port 22: Connection refused

- 터틀봇pc에서 con 즉 'sudo /etc/init.d/ssh restart' 해주기

### 1.3 RLException: Unable to contact my own server at [http://192.168.0.83:33193/]. ~~~

- 이런 에러 뜨면 ~$ gedit ~/.bashrc 들어가서 
  export ROS_MASTER_URI=http://localhost:11311
  export ROS_HOSTNAME=localhost
  위 문장과 비슷한 부분 위 문장으로 바꾸기 그리고 다 끄고 다시 하기

### 1.4  *~~~(선배 졸작을 하던 중에)~~~* 만났던 오류 

#### 1.4.1 catkin build가 안된다면

catkin build에서 src에는 없는데 build에는 있어서 에러가 나는 경우가 있다~ 이럴 때는 한번 build, devel, logs지우고 cm 해보자잉

gmapping가 없다고 하면 
sudo apt-get install ros-melodic-slam-gmapping


map이 없다고 하면
sudo apt-get install ros-indigo-map-server
rosrun map_server map_saver -f ~/map/maptest
vhfej/aoqdlfma

위에 것들 없으면 그냥 아예
https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/#pc-setup 에 1.1.3 Install Dependent ROS 1 Packages 부분 다운

#### 1.4.2 그 외

집게 작동 하려고 따라 해 보기는
https://emanual.robotis.com/docs/en/platform/turtlebot3/manipulation/#turtlebot3-with-openmanipulator 에 1.7 Operate the Actual OpenMANIPULATOR



## 2. 팁

### 2.1 라이다 값 잘 받나 확인

- rostopic echo /scan

### 2.2 커맨드창 열고 닫는 명령어

#### 2.2.1 커맨드 열기

- ctrl + shift + t  : 새 탭

- ctrl + shift + E : 옆에 탭

#### 2.2.2 커맨드 닫기

- ctrl + c 해서 깨끗하게 하고 ctrl + d

### 2.3 move_base_msgs

아니 ros wiki로 ros 다운 받아서 인지 move-base뭐 이런게 없어서 따로 다운 받아주니까 괜찮아 지네ㅎㅎ 

sudo apt install ros-melodic-move-base-msgs



## 3. 터틀봇 ip연결 및 실행

터틀봇을 돌릴려면

![Screenshot from 2020-11-23 19-30-37](https://user-images.githubusercontent.com/52944554/104449160-860e0380-55e1-11eb-96ac-93987e067d46.png)

1. 위 사진처럼 맞춰준다.
2. roscore
3. 새탭
4. ssh pi@터틀봇 ip
5. 터틀봇 이름@터틀봇  에서 roslaunch turtlebot3_bringup turtlebot3_robot.launch
6. 새탭
7. rosrun 패키지 이름 파이썬파일이름.py
