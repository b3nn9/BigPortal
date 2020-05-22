~~~
(base) conda@DA02:~$ sudo apt-get install vino
패키지 목록을 읽는 중입니다... 완료
의존성 트리를 만드는 중입니다       
상태 정보를 읽는 중입니다... 완료
패키지 vino는 이미 최신 버전입니다 (3.22.0-3ubuntu1).
다음 패키지가 자동으로 설치되었지만 더 이상 필요하지 않습니다:
  libfltk-images1.3 libfltk1.3 libvncserver1 x11vnc-data
Use 'sudo apt autoremove' to remove them.
0개 업그레이드, 0개 새로 설치, 0개 제거 및 34개 업그레이드 안 함.
~~~
~~~
(base) conda@DA02:~$ nmcli connection show
NAME                UUID                                  TYPE      DEVICE 
Wired connection 1  f5aa6e13-9748-36fc-b3b5-0694ae0b6ad8  ethernet  enp4s0 
(base) conda@DA02:~$ dconf write /org/gnome/settings-daemon/plugins/sharing/vino-server/enabled-connections "['f5aa6e13-9748-36fc-b3b5-0694ae0b6ad8']"
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
