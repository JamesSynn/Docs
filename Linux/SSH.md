
# SSH

SSH(Secure SHell), 원격에 있는 서버에 접속해 명령을 실행 하거나 파일을 관리하는 프로토콜로 그 역할과 기능은 텔넷과 거의 유사. 텔넷은 암호화하지 않는데, SSH는 모든 데이터를 암호화 한다.
22번 포트 사용

## SSH 서버의 설치

페도라에서는 SSH가 기본 설치 되어 있다.

	$ rpm -qa | grep openssh-server
	openssl-server-<version>.i686
	
	$ ps -e | grep sshd
	1058 ? 00:00:00 sshd
	
SSH가 설치 되어 있고 현재 1058번 PID를 가진 openssh-server가 동작하고 있음을 확인 했다.

## 방화벽 설정

방화벽 상태 알아보기
	
	$ /sbin/service/iptables status
	
방화벽 올리고 내리기

	$ /sbin/service/iptables stop
    $ /sbin/service/iptables start


ssh 설정

	$ sudo emacs /etc/ssh/sshd_config
	
		Port 8103
		AddressFamily inet
		ListenAddress 192.xxx.xxx.1
	
		SyslogFacility AUTHPRIV
		LogLevel INFO
		
		PermitRootLogin no

포트 변경 (/etc/services 파일과 방화벽에서 추가 설정필요)
ipv4에 대해서만 bind
Listen 할 아이피 설정

로그파일이 저장되는 곳 지정 (기본값; /var/log/secure)
로그 레벨 info로 지정해서 웬만한 기록은 다 됨.

ssh 접속시 루트 계정 접속 허용 안 함.



ssh 데몬 재시작

	$ /etc/init.d/sshd restart



	$ sudo emacs /etc/service 


## 서버 접속

	$ ssh <ID>@<SSH server name(IP Address)>
	
현재 시스템에 openssh client가 설치 되었는지 확인

	$ rpm -qa | grep openssh
	
서버 접속

	$ ssh happy@210.xxx.xxx.41
	
	[happy@localhost ~]$
	$ exit
	

	
