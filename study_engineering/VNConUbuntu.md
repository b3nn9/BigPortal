### 우분투 VNC 종결자
- (사전작업) 이런저런 시도를 했다면, 관련 소프트웨어를 다 지운다.
~~~
$ sudo apt-get remove xrdp vnc4server tightvncserver vino
~~~
~~~
$ sudo apt-get install xrdp vino
패키지 목록을 읽는 중입니다... 완료
의존성 트리를 만드는 중입니다       
상태 정보를 읽는 중입니다... 완료
다음의 추가 패키지가 설치될 것입니다 :
  ssl-cert
제안하는 패키지:
  openssl-blacklist guacamole xrdp-pulseaudio-installer
다음 새 패키지를 설치할 것입니다:
  ssl-cert vino xrdp
0개 업그레이드, 3개 새로 설치, 0개 제거 및 2개 업그레이드 안 함.
141 k바이트/560 k바이트 아카이브를 받아야 합니다.
이 작업 후 3,329 k바이트의 디스크 공간을 더 사용하게 됩니다.
계속 하시겠습니까? [Y/n] Y
받기:1 http://mirror.kakao.com/ubuntu bionic/main amd64 ssl-cert all 1.0.39 [17.0 kB]
받기:2 http://mirror.kakao.com/ubuntu bionic/main amd64 vino amd64 3.22.0-3ubuntu1 [124 kB]
내려받기 141 k바이트, 소요시간 0초 (1,089 k바이트/초)
패키지를 미리 설정하는 중입니다...
Selecting previously unselected package ssl-cert.
(데이터베이스 읽는중 ...현재 170432개의 파일과 디렉터리가 설치되어 있습니다.)
Preparing to unpack .../ssl-cert_1.0.39_all.deb ...
Unpacking ssl-cert (1.0.39) ...
Selecting previously unselected package vino.
Preparing to unpack .../vino_3.22.0-3ubuntu1_amd64.deb ...
Unpacking vino (3.22.0-3ubuntu1) ...
Selecting previously unselected package xrdp.
Preparing to unpack .../xrdp_0.9.5-2_amd64.deb ...
Unpacking xrdp (0.9.5-2) ...
vino (3.22.0-3ubuntu1) 설정하는 중입니다 ...
ssl-cert (1.0.39) 설정하는 중입니다 ...
xrdp (0.9.5-2) 설정하는 중입니다 ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for gnome-menus (3.13.3-11ubuntu1.1) ...
Processing triggers for mime-support (3.60ubuntu1) ...
Processing triggers for ureadahead (0.100.0-21) ...
ureadahead will be reprofiled on next reboot
Processing triggers for desktop-file-utils (0.23-1ubuntu3.18.04.2) ...
Processing triggers for libglib2.0-0:amd64 (2.56.4-0ubuntu0.18.04.6) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
Processing triggers for systemd (237-3ubuntu10.41) ...
~~~
~~~
$ nmcli connection show
NAME                UUID                                  TYPE      DEVICE 
Wired connection 1  f5aa6e13-9748-36fc-b3b5-0694ae0b6ad8  ethernet  enp4s0 
$ dconf write /org/gnome/settings-daemon/plugins/sharing/vino-server/enabled-connections "['f5aa6e13-9748-36fc-b3b5-0694ae0b6ad8']"
~~~
~~~
$ sudo vi /etc/xrdp/xrdp.ini
~~~
~~~
(base) conda@DA02:~$ sudo reboot
~~~
~~~
(base) conda@DA02:~$ netstat -na | grep 59
tcp        0      0 0.0.0.0:5900            0.0.0.0:*               LISTEN     
tcp6       0      0 :::5900                 :::*                    LISTEN     
unix  2      [ ACC ]     STREAM     LISTENING     1959     /run/user/1000/bus
unix  2      [ ]         DGRAM                    19420    /var/run/nvidia-xdriver-edf59000
unix  3      [ ]         DGRAM                    19419    @var/run/nvidia-xdriver-edf59000@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
unix  3      [ ]         STREAM     CONNECTED     34759    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     29590    
unix  3      [ ]         STREAM     CONNECTED     28591    @/tmp/.X11-unix/X0
unix  3      [ ]         STREAM     CONNECTED     29592    
unix  3      [ ]         STREAM     CONNECTED     28598    @/tmp/.X11-unix/X0
unix  3      [ ]         STREAM     CONNECTED     29591    
unix  3      [ ]         STREAM     CONNECTED     29597    
unix  3      [ ]         STREAM     CONNECTED     22159    @/tmp/dbus-VwTo1uFv
unix  3      [ ]         STREAM     CONNECTED     22459    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     28596    
unix  3      [ ]         STREAM     CONNECTED     28595    
unix  3      [ ]         STREAM     CONNECTED     23359    
~~~
~~~
(base) conda@DA02:~$ sudo gsettings set org.gnome.Vino require-encryption false
[sudo] conda의 암호: 
(process:2048): dconf-WARNING **: 16:27:26.915: failed to commit changes to dconf: X11 $DISPLAY 없이 D-Bus 자동 실행할 수 없습니다
(base) conda@DA02:~$ export DISPLAY=:0.0
(base) conda@DA02:~$ sudo gsettings set org.gnome.Vino require-encryption false
(process:2055): dconf-WARNING **: 16:28:47.085: failed to commit changes to dconf: “dbus-launch --autolaunch=feb861016fda43b987d2581d086d7049 --binary-syntax --close-stderr” 명령을 시작하는데 오류: 하위 프로세스가 1 코드로 끝났습니다
(base) conda@DA02:~$ xhost +
access control disabled, clients can connect from any host
~~~
~~~
(base) conda@DA02:~$ sudo reboot
~~~
~~~

~~~
