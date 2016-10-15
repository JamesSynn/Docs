
# Oh-my-zsh


Main: https://github.com/robbyrussell/oh-my-zsh
Install: https://gist.github.com/jshcrowthe/f0779322ecf9a26cac30
Themes : https://github.com/robbyrussell/oh-my-zsh/wiki/themes

## Installing ZSH

	$ sudo dnf install zsh
	
## install oh-my-zsh

	$ wget --no-check-certificate http://install.ohmyz.sh -O - | sh
	
## Changing your shell

	$ sudo chsh -s /usr/bin/zsh
	
	
	Try other way:
	
	$ chsh -s /bin/zsh user
	$ sudo chsh -s /bin/zsh james
	$ finger james | grep zsh

	Directory: /home/james Shell: /bin/zsh

## Updating your .zshcr 

	$ gedit ~/.zshrc
	
	
Then copy and paste the following block at the BOTTOM of the file:

	# Set the JAVA_HOME path.
	export JAVA_HOME=/usr/lib/jvm/java-1.7.0-openjdk-1.7.0.75-2.5.4.2.fc20.x86_64

	# Set the CLASSPATH path.
	export CLASSPATH=/usr/share/java/mysql-connector-java.jar:.

	# User specific aliases and functions
	. /u01/app/oracle/product/11.2.0/xe/bin/oracle_env.sh

	# Wrap sqlplus with rlwrap to edit prior lines with the
	# up, down, left and right keys.
	sqlplus()
	{
		if [ "$RLWRAP" = "0" ]; then
			sqlplus "$@"
		else
			rlwrap sqlplus "$@"
		fi
	}

	# Set the bindkey.
	bindkey -v
	bindkey "^R" history-incremental-search-backward
	export EDITOR="vim"

	# history stuff
	HISTFILE=~/.zsh-histfile
	HISTSIZE=2000

	# Set vi as a command line editor.
	set -o vi
	
	
## Configuring oh-my-zsh
	
Theme
By default the oh-my-zsh theme is set to robbyrussell. I personally don't like this I prefer a modified version of a different theme. On line 8 change

	ZSH_THEME="robbyrussell"

TO:

	ZSH_THEME="agnoster"


## Installing the font

There is probably a better way to do this BUT I am just trying to get this to work and this is what I found that works. Only if you simply downloaded the file into the downloads directory then executing the following command will take care of the copy and install.

*NOTE: If you downloaded the file into a different directory then simply replace ~/Downloads/Inconsolata+for+Powerline.otf with the path to your file

	sudo mkdir /usr/share/fonts/inconsolata && sudo cp ~/Downloads/Inconsolata+for+Powerline.otf /usr/share/fonts/inconsolata/inconsolata.otf && sudo fc-cache -v

