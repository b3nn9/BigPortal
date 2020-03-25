## 우분투에 CUDA 설치하기
~~~
(base) conda@da02:/etc/apt/sources.list.d$ sudo bash -c 'echo "deb http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64 /" > /etc/apt/sources.list.d/cuda.list' cs
(base) conda@da02:/etc/apt/sources.list.d$ sudo apt-get update
~~~
~~~
(base) conda@da02:/etc/apt/sources.list.d$ sudo apt-get install nvidia-driver-440
패키지 목록을 읽는 중입니다... 완료
의존성 트리를 만드는 중입니다       
상태 정보를 읽는 중입니다... 완료
다음 패키지가 자동으로 설치되었지만 더 이상 필요하지 않습니다:
  cuda-command-line-tools-10-2 cuda-compiler-10-2 cuda-cudart-10-2 cuda-cudart-dev-10-2 cuda-cufft-10-2 cuda-cufft-dev-10-2 cuda-cuobjdump-10-2 cuda-cupti-10-2
  cuda-cupti-dev-10-2 cuda-curand-10-2 cuda-curand-dev-10-2 cuda-cusolver-10-2 cuda-cusolver-dev-10-2 cuda-cusparse-10-2 cuda-cusparse-dev-10-2 cuda-documentation-10-2
  cuda-driver-dev-10-2 cuda-gdb-10-2 cuda-libraries-10-2 cuda-libraries-dev-10-2 cuda-license-10-2 cuda-memcheck-10-2 cuda-misc-headers-10-2 cuda-npp-10-2
  cuda-npp-dev-10-2 cuda-nsight-10-2 cuda-nsight-compute-10-2 cuda-nsight-systems-10-2 cuda-nvcc-10-2 cuda-nvdisasm-10-2 cuda-nvgraph-10-2 cuda-nvgraph-dev-10-2
  cuda-nvjpeg-10-2 cuda-nvjpeg-dev-10-2 cuda-nvml-dev-10-2 cuda-nvprof-10-2 cuda-nvprune-10-2 cuda-nvrtc-10-2 cuda-nvrtc-dev-10-2 cuda-nvtx-10-2 cuda-nvvp-10-2
  cuda-samples-10-2 cuda-sanitizer-api-10-2 cuda-toolkit-10-2 cuda-tools-10-2 cuda-visual-tools-10-2 lib32gcc1 libc6-i386 libcublas-dev libcublas10 libwayland-egl1-mesa
  nsight-compute-2019.5.0 nsight-systems-2019.5.2 nvidia-modprobe
Use 'sudo apt autoremove' to remove them.
다음의 추가 패키지가 설치될 것입니다 :
  libnvidia-cfg1-440 libnvidia-compute-440 libnvidia-decode-440 libnvidia-encode-440 libnvidia-fbc1-440 libnvidia-gl-440 libnvidia-ifr1-440 nvidia-compute-utils-440
  nvidia-dkms-440 nvidia-kernel-source-440 nvidia-utils-440 xserver-xorg-video-nvidia-440
추천하는 패키지:
  libnvidia-compute-440:i386 libnvidia-decode-440:i386 libnvidia-encode-440:i386 libnvidia-ifr1-440:i386 libnvidia-fbc1-440:i386 libnvidia-gl-440:i386
다음 패키지를 지울 것입니다:
  libcuda1-340 nvidia-opencl-icd-340
다음 새 패키지를 설치할 것입니다:
  libnvidia-cfg1-440 libnvidia-compute-440 libnvidia-decode-440 libnvidia-encode-440 libnvidia-fbc1-440 libnvidia-gl-440 libnvidia-ifr1-440 nvidia-compute-utils-440
  nvidia-dkms-440 nvidia-driver-440 nvidia-utils-440 xserver-xorg-video-nvidia-440
다음 패키지를 업그레이드할 것입니다:
  nvidia-kernel-source-440
1개 업그레이드, 12개 새로 설치, 2개 제거 및 11개 업그레이드 안 함.
5개를 완전히 설치하지 못했거나 지움.
100 M바이트 아카이브를 받아야 합니다.
이 작업 후 276 M바이트의 디스크 공간을 더 사용하게 됩니다.
계속 하시겠습니까? [Y/n] Y
받기:1 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  libnvidia-cfg1-440 440.64.00-0ubuntu1 [71.3 kB]
받기:2 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  libnvidia-compute-440 440.64.00-0ubuntu1 [20.9 MB]
받기:3 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  libnvidia-decode-440 440.64.00-0ubuntu1 [1,026 kB]                                       
받기:4 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  libnvidia-encode-440 440.64.00-0ubuntu1 [38.0 kB]                                        
받기:5 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  libnvidia-fbc1-440 440.64.00-0ubuntu1 [48.9 kB]                                          
받기:6 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  libnvidia-gl-440 440.64.00-0ubuntu1 [62.9 MB]                                            
47% [6 libnvidia-gl-440 26.9 MB/62.9 MB 43%]                                                                                                            198 kB/s 4분 19초^[[받기:7 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  libnvidia-ifr1-440 440.64.00-0ubuntu1 [68.5 kB]                                          
받기:8 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  nvidia-compute-utils-440 440.64.00-0ubuntu1 [73.7 kB]                                    
받기:9 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  nvidia-kernel-source-440 440.64.00-0ubuntu1 [13.2 MB]                                    
받기:10 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  nvidia-dkms-440 440.64.00-0ubuntu1 [26.3 kB]                                            
받기:11 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  nvidia-utils-440 440.64.00-0ubuntu1 [345 kB]                                            
받기:12 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  xserver-xorg-video-nvidia-440 440.64.00-0ubuntu1 [1,478 kB]                             
받기:13 http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  nvidia-driver-440 440.64.00-0ubuntu1 [409 kB]                                           
내려받기 100 M바이트, 소요시간 5분 53초 (285 k바이트/초)                                                                                                                   
(데이터베이스 읽는중 ...현재 155085개의 파일과 디렉터리가 설치되어 있습니다.)
Removing libcuda1-340 (340.107-0ubuntu0.18.04.4) ...
Removing nvidia-opencl-icd-340 (340.107-0ubuntu0.18.04.4) ...
Selecting previously unselected package libnvidia-cfg1-440:amd64.
(데이터베이스 읽는중 ...현재 155069개의 파일과 디렉터리가 설치되어 있습니다.)
Preparing to unpack .../00-libnvidia-cfg1-440_440.64.00-0ubuntu1_amd64.deb ...
Unpacking libnvidia-cfg1-440:amd64 (440.64.00-0ubuntu1) ...
Selecting previously unselected package libnvidia-compute-440:amd64.
Preparing to unpack .../01-libnvidia-compute-440_440.64.00-0ubuntu1_amd64.deb ...
Unpacking libnvidia-compute-440:amd64 (440.64.00-0ubuntu1) ...
Selecting previously unselected package libnvidia-decode-440:amd64.
Preparing to unpack .../02-libnvidia-decode-440_440.64.00-0ubuntu1_amd64.deb ...
Unpacking libnvidia-decode-440:amd64 (440.64.00-0ubuntu1) ...
Selecting previously unselected package libnvidia-encode-440:amd64.
Preparing to unpack .../03-libnvidia-encode-440_440.64.00-0ubuntu1_amd64.deb ...
Unpacking libnvidia-encode-440:amd64 (440.64.00-0ubuntu1) ...
Selecting previously unselected package libnvidia-fbc1-440:amd64.
Preparing to unpack .../04-libnvidia-fbc1-440_440.64.00-0ubuntu1_amd64.deb ...
Unpacking libnvidia-fbc1-440:amd64 (440.64.00-0ubuntu1) ...
Selecting previously unselected package libnvidia-gl-440:amd64.
Preparing to unpack .../05-libnvidia-gl-440_440.64.00-0ubuntu1_amd64.deb ...
/usr/lib/x86_64-linux-gnu/libGL.so.1의 /usr/lib/x86_64-linux-gnu/libGL.so.1.distrib(으)로 전환, nvidia-340 패키지
dpkg-divert: 오류: <패키지>에 문제 발생
  '/usr/lib/x86_64-linux-gnu/libGL.so.1의 전환, libnvidia-gl-440 패키지' 지우는 중
  '/usr/lib/x86_64-linux-gnu/libGL.so.1의 /usr/lib/x86_64-linux-gnu/libGL.so.1.distrib(으)로 전환, nvidia-340 패키지' 발견
dpkg: error processing archive /tmp/apt-dpkg-install-CjNxXz/05-libnvidia-gl-440_440.64.00-0ubuntu1_amd64.deb (--unpack):
 new libnvidia-gl-440:amd64 package pre-installation script subprocess returned error exit status 2
Selecting previously unselected package libnvidia-ifr1-440:amd64.
Preparing to unpack .../06-libnvidia-ifr1-440_440.64.00-0ubuntu1_amd64.deb ...
Unpacking libnvidia-ifr1-440:amd64 (440.64.00-0ubuntu1) ...
Selecting previously unselected package nvidia-compute-utils-440.
Preparing to unpack .../07-nvidia-compute-utils-440_440.64.00-0ubuntu1_amd64.deb ...
Unpacking nvidia-compute-utils-440 (440.64.00-0ubuntu1) ...
Preparing to unpack .../08-nvidia-kernel-source-440_440.64.00-0ubuntu1_amd64.deb ...
Unpacking nvidia-kernel-source-440 (440.64.00-0ubuntu1) over (440.33.01-0ubuntu1) ...
Selecting previously unselected package nvidia-dkms-440.
Preparing to unpack .../09-nvidia-dkms-440_440.64.00-0ubuntu1_amd64.deb ...
Unpacking nvidia-dkms-440 (440.64.00-0ubuntu1) ...
Selecting previously unselected package nvidia-utils-440.
Preparing to unpack .../10-nvidia-utils-440_440.64.00-0ubuntu1_amd64.deb ...
Unpacking nvidia-utils-440 (440.64.00-0ubuntu1) ...
Selecting previously unselected package xserver-xorg-video-nvidia-440.
Preparing to unpack .../11-xserver-xorg-video-nvidia-440_440.64.00-0ubuntu1_amd64.deb ...
Unpacking xserver-xorg-video-nvidia-440 (440.64.00-0ubuntu1) ...
Selecting previously unselected package nvidia-driver-440.
Preparing to unpack .../12-nvidia-driver-440_440.64.00-0ubuntu1_amd64.deb ...
Unpacking nvidia-driver-440 (440.64.00-0ubuntu1) ...
처리하는데 오류가 발생했습니다:
 /tmp/apt-dpkg-install-CjNxXz/05-libnvidia-gl-440_440.64.00-0ubuntu1_amd64.deb
E: Sub-process /usr/bin/dpkg returned an error code (1)

~~~
