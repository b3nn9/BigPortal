## 우분투 18.04 VNC 설정과 모니터없이 원격하기
- 자동 로그인 설정 : [root 자동 로그인 설정](https://ssup2.github.io/record/Auto_root_Login_%EC%84%A4%EC%A0%95_Ubuntu_18.04/)
~~~
$ sudo vi /etc/gdm3/custom.conf
......
AutomaticLoginEnable = true
AutomaticLogin = [자동 로그인하려는 계정]
......
~~~
- 

$ sudo apt install x11vnc
~~~
[sudo] password for conda: 
패키지 목록을 읽는 중입니다... 완료
의존성 트리를 만드는 중입니다       
상태 정보를 읽는 중입니다... 완료
The following additional packages will be installed:
  libtcl8.6 libtk8.6 libvncserver1 tcl tcl8.6 tk tk8.6 x11vnc-data
제안하는 패키지:
  tcl-tclreadline
다음 새 패키지를 설치할 것입니다:
  libtcl8.6 libtk8.6 libvncserver1 tcl tcl8.6 tk tk8.6 x11vnc x11vnc-data
0개 업그레이드, 9개 새로 설치, 0개 제거 및 107개 업그레이드 안 함.
2,914 k바이트 아카이브를 받아야 합니다.
이 작업 후 9,555 k바이트의 디스크 공간을 더 사용하게 됩니다.
계속 하시겠습니까? [Y/n] Y
받기:1 http://kr.archive.ubuntu.com/ubuntu bionic/main amd64 libtcl8.6 amd64 8.6.8+dfsg-3 [881 kB]
받기:2 http://kr.archive.ubuntu.com/ubuntu bionic/main amd64 libtk8.6 amd64 8.6.8-4 [693 kB]
받기:3 http://kr.archive.ubuntu.com/ubuntu bionic-updates/main amd64 libvncserver1 amd64 0.9.11+dfsg-1ubuntu1.1 [122 kB]
받기:4 http://kr.archive.ubuntu.com/ubuntu bionic/main amd64 tcl8.6 amd64 8.6.8+dfsg-3 [14.4 kB]
받기:5 http://kr.archive.ubuntu.com/ubuntu bionic/universe amd64 tcl amd64 8.6.0+9 [5,146 B]
받기:6 http://kr.archive.ubuntu.com/ubuntu bionic/main amd64 tk8.6 amd64 8.6.8-4 [12.3 kB]
받기:7 http://kr.archive.ubuntu.com/ubuntu bionic/universe amd64 tk amd64 8.6.0+9 [3,178 B]
받기:8 http://kr.archive.ubuntu.com/ubuntu bionic/universe amd64 x11vnc-data all 0.9.13-3 [214 kB]
받기:9 http://kr.archive.ubuntu.com/ubuntu bionic/universe amd64 x11vnc amd64 0.9.13-3 [967 kB]
내려받기 2,914 k바이트, 소요시간 3초 (942 k바이트/초)
Selecting previously unselected package libtcl8.6:amd64.
(데이터베이스 읽는중 ...현재 130346개의 파일과 디렉터리가 설치되어 있습니다.)
Preparing to unpack .../0-libtcl8.6_8.6.8+dfsg-3_amd64.deb ...
Unpacking libtcl8.6:amd64 (8.6.8+dfsg-3) ...
Selecting previously unselected package libtk8.6:amd64.
Preparing to unpack .../1-libtk8.6_8.6.8-4_amd64.deb ...
Unpacking libtk8.6:amd64 (8.6.8-4) ...
Selecting previously unselected package libvncserver1:amd64.
Preparing to unpack .../2-libvncserver1_0.9.11+dfsg-1ubuntu1.1_amd64.deb ...
Unpacking libvncserver1:amd64 (0.9.11+dfsg-1ubuntu1.1) ...
Selecting previously unselected package tcl8.6.
Preparing to unpack .../3-tcl8.6_8.6.8+dfsg-3_amd64.deb ...
Unpacking tcl8.6 (8.6.8+dfsg-3) ...
Selecting previously unselected package tcl.
Preparing to unpack .../4-tcl_8.6.0+9_amd64.deb ...
Unpacking tcl (8.6.0+9) ...
Selecting previously unselected package tk8.6.
Preparing to unpack .../5-tk8.6_8.6.8-4_amd64.deb ...
Unpacking tk8.6 (8.6.8-4) ...
Selecting previously unselected package tk.
Preparing to unpack .../6-tk_8.6.0+9_amd64.deb ...
Unpacking tk (8.6.0+9) ...
Selecting previously unselected package x11vnc-data.
Preparing to unpack .../7-x11vnc-data_0.9.13-3_all.deb ...
Unpacking x11vnc-data (0.9.13-3) ...
Selecting previously unselected package x11vnc.
Preparing to unpack .../8-x11vnc_0.9.13-3_amd64.deb ...
Unpacking x11vnc (0.9.13-3) ...
x11vnc-data (0.9.13-3) 설정하는 중입니다 ...
libvncserver1:amd64 (0.9.11+dfsg-1ubuntu1.1) 설정하는 중입니다 ...
libtcl8.6:amd64 (8.6.8+dfsg-3) 설정하는 중입니다 ...
libtk8.6:amd64 (8.6.8-4) 설정하는 중입니다 ...
tcl8.6 (8.6.8+dfsg-3) 설정하는 중입니다 ...
tk8.6 (8.6.8-4) 설정하는 중입니다 ...
tcl (8.6.0+9) 설정하는 중입니다 ...
tk (8.6.0+9) 설정하는 중입니다 ...
x11vnc (0.9.13-3) 설정하는 중입니다 ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for gnome-menus (3.13.3-11ubuntu1.1) ...
Processing triggers for mime-support (3.60ubuntu1) ...
Processing triggers for desktop-file-utils (0.23-1ubuntu3.18.04.2) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
~~~
$ sudo vi /etc/systemd/system/x11vnc.service
~~~
# Description: Custom Service Unit file
# File: /lib/systemd/system/x11vnc.service
[Unit]
Description="x11vnc"
Requires=display-manager.service
After=display-manager.service

[Service]
ExecStart=/usr/bin/x11vnc -loop -nopw -xkb -repeat -noxrecord -noxfixes -noxdamage -forever -rfbport 5900 -display :0 -auth guess
ExecStop=/usr/bin/killall x11vnc
Restart=on-failure
Restart-sec=2

[Install]
WantedBy=multi-user.target
~~~
$ sudo systemctl enable x11vnc.service
~~~
Created symlink /etc/systemd/system/multi-user.target.wants/x11vnc.service → /etc/systemd/system/x11vnc.service.
~~~
