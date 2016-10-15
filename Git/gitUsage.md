
# GIT

ref.
https://opentutorials.org/course/1492
https://github.com
https://bitbucket.org

## git initializing

### start git

	$ mkdir workbench
	$ cd workbench
	
	$ git init
	$ ls -a
	
폴더 생성과 폴더 이동 후,
저장소 초기화 .git 디렉토리 생성(깃파일 생성과 변경이력 보관)

### 사용자 이름 이메일 등록

	$ git config --global user.name "JamesSynn"
	$ git config --global user.email "jamessynn@gmail.com"
	$ git config --local user.name "JamesNote"
	$ git config --local user.email "jamessynn@gmail.com"
	$ git config -l

### 디렉토리에  파일 추가

	$ git status
	$ git add content.docx
	
(optional)

	$ git add . # 변경 사항만
	$ git add *  # 모든 파일
	$ git add *.docx  # docx의 확장자를 가진 파일들만

###  제외하고 싶은 파일 설정 (optional)

임시파일이나 폴더, 자동 저장등으로 생성된 파일을 제외 할 수 있다.

	$ git status
	$ emacs .gitignore

	.gitignore 
		제외하고싶은 파일 설정
		ex) contents: ~*.* # 임시파일 제 외

### 추가 되돌리기(option)

	$ git reset filename.extension

### 파일 커밋(새로운 단계 규정)

	$ git commit -m "your comments for the commit"

### 체크 아웃(이력간의 이동)

	$ git log  # 저장소 이력
	$ git check ___commit_id___

	$ git checkout master #최근변경사항으로 되돌림


## git 실행 명령

 명령 패턴

	$ git <operation_keyword> <parameter> and/or <values>

	git clone # 깃의 복제
	git fetch # 소스부터 목적지까지 변경사항
	git merge # 분기를 하나로 합침
	git push # 소스를 목적지에 밀어넣음
	git remote # 소스와 목적지를 관리(fetch, push, pull)


### 저장소에 원격지를 연결하거나 추가하는 방법

	$ cd ~/Documents/Docs
	$ git remote add docs https://github.com/JamesSynn/Docs.git
	$ git push -u docs master
	
add 와 push 에 있는 origin은 다른 이름으로 대체 가능, 두 개가 같아야 함 
저장소 별로 원격지 를 설정해 주어야 한다.

	$ git config -l 

##  git을 사용해 작업하기

	$ git clone https://github.com/JamesSynn/Docs.git ~/Documents/Docs  # 로컬에 저장소 생성
/Docs라는 디렉토리는 로컬에 존재하지 않아야 한다.
클론을 하면 /Docs 안에 자동으로 로컬저장소와 .git 디렉토리 그리고 origin이 설정된다.
따라서, 작업 후 아래 명령만 입력하면 된다.

 디렉토리 이동

	$ cd ~/Documents/Docs

~/Documents/Docs

	$ git add .  #  변경사항 저장
	$ git commit -m "your commit message"  #  저장된 파일 커밋
	$ git pull  # 로컬 저장소 업데이트
	$ git push  # 온라인으로 업로드 


### 노출된 저장소 생성 (optional)

 원격지를 bitbucket으로 생성했을 때, 저장소를 복사해서 오픈된 저장소로 코드를 노출 할 수 있다.

	$ git clone --bare c:/user/workbench c:/share/bare_workbench

## 디테일한 사용

	$ git <command> -h #  도움말, 명령어 상세 보기

### remote 명령

	$ git remote add <name> <url>  #  원격지 추가
	$ git remote rename <old> <new>  #   원격지 이름 변경
	$ git remote remove <name> # 제거
	
	
