
# Telnet

 텔넷은 원격지에 존재하는 호스트에 원격으로 접속하는 TCP/IP 기반 프로토콜이다.
 
## 텔넷 서버의 설치 및 설정 과정
 
1) 텔넷 서버를 설치 한다.
2) 텔넷 서버의 설정 파일을 변경한다.
3) xinetd 데몬을 재시작 한다.
4) 텔넷 사용자를 생성한다.
5) 방화벽 설정을 변경한다.
6) 클라이언트에서 접속 프로그램을 사용해 텔넷 서버에 접속한다.

## 텔넷 서버의 설치

	$ sudo dnf -y install telnet-server
	$ sudo rpm -qa | grep telnet
	telnet-server-<version>.i686
	telnet-<version>.i686
	
## 텔넷 설정

	$ sudo emacs /etc/xinetd.d/telnet
	
	telnet>
	# default:on
	# description: The telnet server serves telnet sessions' int uses\
	# unencrypted userhome / password pairs for authentication.
	
	service telnet
	{
		flags       = REUSE
		socket_type = stream
		wait        = no
		user        = root
		server      = /usr/sbin/in.telnetd
		log_on_failure += USERID
		disable     = yes
	}
	
	$ emacs /etc/xinet.d/telnet
	
	
		disable     = no
	}
	
텔넷 서버의 사용 유무를 지정한다. 텔넷을 사용하려면 no, 사용하지 않으려면 yes로 설정한다.

xinetd 데몬을 재가동

	$ sudo /etc/rc.d/init.d/xinetd restart
	Restarting xinetd (via systemctl):  [O K]


## 텔넷 접속

	$ sudo useradd happy
	$ sudo passwd happy
	
## 방화벽 설정

	23번 포트 telnet으로 설정
	
## 텔넷을 이용한 원격 접속


	$ sudo telnet 210.xxx.xxx.41
	
	Trying 210.xxx.xxx.41...
	Connected to 210.xxx.xxx.41.
	Escape character is '^]'.
	Fedora release 25 (Lovelock)
	Kernel <version>
	login:
	
서버 접속에 성공했다면 pwd 명령을 사용해 현재 위치를 확인

	$ pwd
	/home/happy
	$ exit

접속해재

## 부가 설정

	$ emacs /opt/xinetd.d/telnet
	
		disable     = no
		only_from   = 210.xxx.xxx.39   # 39 IP만 접속 가능
		no_access   = 210.xxx.xxx.38   # 38 IP만 접속 불가
		instances   = 100              # 접속자 수 100명 제한
		access_time = 09:00~18:00      # 접속 허용 시간
		per_source  = 3                # 동일한 IP에서 3번 이상 접속 차단
	                                     (DDos 공격 방지를 위함)




