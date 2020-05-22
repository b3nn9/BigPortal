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
(base) conda@DA02:~$ sudo gsettings set org.gnome.Vino require-encryption false
[sudo] conda의 암호: 
(process:2048): dconf-WARNING **: 16:27:26.915: failed to commit changes to dconf: X11 $DISPLAY 없이 D-Bus 자동 실행할 수 없습니다
(base) conda@DA02:~$ export DISPLAY=:0.0
(base) conda@DA02:~$ sudo gsettings set org.gnome.Vino require-encryption false
(process:2055): dconf-WARNING **: 16:28:47.085: failed to commit changes to dconf: “dbus-launch --autolaunch=feb861016fda43b987d2581d086d7049 --binary-syntax --close-stderr” 명령을 시작하는데 오류: 하위 프로세스가 1 코드로 끝났습니다
(base) conda@DA02:~$ xhost +
access control disabled, clients can connect from any host
~~~
