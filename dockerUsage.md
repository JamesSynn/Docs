
# Docker 

## Docker Install

~~~bash

	$ curl -s https://get.docker.io | sudo sh
	$ docker -v # docker version check
	
	#  방화벽 설정 (optional)
	$ sudo ufw allow 4243/tcp #  도커가 사용하는 4243/tcp port Open
	
	#  자동 도커 사용 (optional)
	$ sudo groupadd docker # adding group
	$ sudo gpasswd -a ${user} docker # 패스워드 입력 불필요
	$ sudo service docker restart # docker  자동 실행
	
~~~

## Docker Start

~~~ bash 
	
	$ sudo service docker start

	$ sudo docker search # docker 이미지 찾기
	
	
~~~
