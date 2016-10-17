
# Cask 

## What is Cask?

Cask는 Emacs의 패키지 관리를 위한 툴이다.
각종 패키지들을 저장소로부터 자동으로 얻어오고 특정 버전을 지정하거나 최신 버전으로 쉽게 업데이트 할 수 있다.

## Install 

Emacs24  버전 이상이  설치되어 있어야한다.
아래 두가지 방법 중 선택

### Auto install

	$ curl -fsSkL https://raw.github.com/cask/cask/master/go | python

### 저장소 클론으로 설치

	$ git clone https://github.com/cask/cask.git ~/.cask

### Path 설정

	$ export PATH="$HOME/.cask/bin:$PATH"

### Path 확인 (optional)

	$ export -p 
 출력된 PATH 에 .cask  경로가 추가되어 있지 않으면 cask 명령을 실행할 수 없다.

### 설치 확인, 업그레이드

	$ cask upgrade-cask

설치가 완료되면 위 명령을 실행할 수 있다. 안되면 설치가 안된 것.

### 설치가 안됐을 때 (optional)

cask가 불완전하게 설치 됐을때 재설치가 불가능하다.  이때, ~/.cask  디렉토리를 지워야 한다.

	$ rm -f -r ~/.cask # 디렉토리 삭제

 이후 다시 설치하면 된다.


## Usage

### initial Setting

 처음 사용할 때에, Emacs Lisp Project route 에 Cask 파일을 만들어야 한다.
init 명령을 통해 .cask  디렉토리와 Cask 파일을 자동으로 생성할 수 있다.

	$ cd ~/.emacs.d
	$ cask init

~/.emacs.d  내부에 emacs 설정파일인 init.el 파일을 만들어 아래 내용을 추가한다.

~/.emacs.d/init.el
	(require 'cask "~/.cask/cask.el")
		(cask-initialize)

### 모든의존 라이브러리 설치

	$ cd ~/.emacs.d
	$ cask install

Cask 파일이 .emacs.d 디렉토리에 있기 때문에 이곳에서 cask 명령을 실행한다.
주의) Cask 파일에 입력된 패키지를 모두 다운로드 하기 때문에 오래 걸린다.

### Init-Loader






Cask Online Documents
http://cask.readthedocs.io/en/latest/index.html
