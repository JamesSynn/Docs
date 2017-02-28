

# VNC

VNC는 서버간 X윈도우 환경(GUI)에서 원격으로 시스템에 접속할 수 있도록 해준다.
원격으로 접속해 GUI 환경으로 시스템을 사용할 수 있다는 장점이 있지만 몇가지 단점을 포함하고 있다. 속도, 클라이언트설치 ..


## VNC 서버의 설치 및 설정 과정

1) VNC 서버를 설치한다.
2) VNC 서버접속 환경을 설정하고 사용자를 등록한다.
3) VNC 서버를 가동한다.
4) 방화벽을 설정한다.
5) VNC 클라이언트를 설치한다.
6) 클라이언트에서 접속한다.

## VNC 서버의 설치

	$ sudo dnf -y install tigervnc-server
	$ rpm -qa | grep tigervnc
	$ sudo emacs /etc/sysconfig/vncservers
	
		VNCSERVERS = "1:root" # 디스플레이 번호와 사용자 계정
	
	$ sudo cd /root
	root # mkdir .vnc
	root # cd .vnc
	.vnc # vncpasswd
	
	.vnc # ls -al
	.vnc # cd /root
	
	root # service vncserver start
	starting vncserver(via systemctl):
	
## 방화벽 설정


## VNC를 이용한 원격 접속

vncviewer <server IP>:<display number>

	$ sudo dnf -y install tigervnc
	$ rpm -qa | grep tigervnc
	$ sudo vncviewer 210.xxx.xxx.41:1
	password
	
	
