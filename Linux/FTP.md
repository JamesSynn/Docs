
# FTP

FTP(File Transfer Protocol)은 네트워크에 존재하는 컴퓨터들 사이에 파일을 전송하기 위한 네트워크 서비스이다. 최근 www서비스를 통해서도 파일을 전송할 수 있게 되었으며, 많은 사이트에서 FTP와 www 서비스를 동시에 사용한다. 
리눅스에서는 vsFTPD(very secure FTPD)를 사용한다. Cris Evans에 의해 개발 되었고 기존 FTP의 취약성을 보완하여 시스템을 공격할 수 없도록 설계되어 강력한 보안 기능을 제공해 많이 사용된다.

FTP 서비스는 standard 방식이나 inetd 방식 모두 사용할 수 있다. 일반적으로 inetd 방식을 사용한다.

## FTP 사용 절차

1) vsFTPD 서버를 설치한다.
2) vsFTPD 서버 접속 환경을 설정한다.
3) vsFTPD 서버를 가동한다.
4) 방화벽 설정을 변경한다.
5) FTP 클라이언트를 통해 접속한다.

## 서버설치와 확인

	$ sudo dnf -y install vsftpd
	$ rpm -qa | grep vsftp
	
## 서버 환경설정


