# HyeWonWiki

# 오류 & 팁 & 실수

## 0. 선배님께 질문하기 전에 체크

- .py 파일 실행권한 주기

- package 만들고 cm

- ros master uri, hostname 바꾸기 , source ~/.bashrc

- roscore 노드 키는거

  rosrun 패키지이름 노드이름.py그거

  roslaunch 는 런치파일 키는거

- 터미널 껐다가 켜보기

- roscore가 실행이 안된다면 localhost자리에 아이피가 쓰여있으면 바꿔야지~

## 1. 오류

### 1.1 turtlebot이 안 멈출때

- rosrun turtlebot3_teleop turtlebot3_teleop_key (단축말tele)



### 1.2 ssh: connect to host 192.168.0.34 port 22: Connection refused

- 터틀봇pc에서 con 즉 'sudo /etc/init.d/ssh restart' 해주기

 

### 1.3 RLException: Unable to contact my own server at [http://192.168.0.83:33193/]. ~~~

- 이런 에러 뜨면 ~$ gedit ~/.bashrc 들어가서 
  export ROS_MASTER_URI=http://localhost:11311
  export ROS_HOSTNAME=localhost
  위 문장과 비슷한 부분 위 문장으로 바꾸기
- 그리고 다 끄고 다시 하기

### 1.4  (선배 졸작을 하던 중에) catkin build가 안됟나면

catkin build에서 src에는 없는데 build에는 있어서 에러가 나는 경우가 있다~이럴 때는 한번 build, devel, logs지우고 cm 해봥

 no gmapping
sudo apt-get install ros-melodic-slam-gmapping



## 2. 팁

### 2.1 라이다 값 잘 받나 확인

- rostopic echo /scan



### 2.2 커맨드창 열고 닫는 명령어

#### 2.2.1 커맨드 열기

- ctrl + shift + t  : 새 탭

- ctrl + shift + E : 옆에 탭

#### 2.2.2 커맨드 닫기

- ctrl + c 해서 깨끗하게 하고 ctrl + d

### 2.3 move_base_msga

아니 ros wiki로 ros 다운 받아서 인지 move-base뭐 이런게 없어서 따로 다운 받아주니까 괜찮아 지네ㅎㅎ 

sudo apt install ros-melodic-move-base-msgs





## 3. 실수



## 4. 기억해

터틀봇을 돌릴려면

![Screenshot from 2020-11-23 19-30-37](/home/won/Pictures/Screenshot from 2020-11-23 19-30-37.png)

1. 위 사진처럼 맞춰준다.
2. roscore
3. 새탭
4. ssh pi@192.168.0.45
5. pi@pi 에서 roslaunch turtlebot3_bringup turtlebot3_robot.launch
6. 새탭
7. rosrun 패키지 이름 파이썬파일이름.py
