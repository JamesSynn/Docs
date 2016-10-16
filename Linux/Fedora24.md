
# Fedora24 

## Fedora?


## Install


## Environment Setting

### Do a Full System Update
   
Issue the following command to update your system:

	/# dnf update


### Configure System Hostname

To check your hostname, run the command below:
	
	/# hostnamectl 
	
Change your hostname as follows:

	/# hostnamectl set-hostname "jCom"
	
	
### Configure a Static IP Address

Using your favorite editor, open and edit enp0s3 or eth0 network configuration file under the directory /etc/sysconfig/network-scripts/ file.

	/# vi /etc/sysconfig/network-scripts/ifcfg-enp0s3

	BOOTPROTO=static
	ONBOOT=yes
	IPADDR=192.168.1.1
	NETMASK=255.255.255.0
	GATEWAY=192.168.1.1
	DNS1=202.88.131.90
	DNS2=202.88.131.89

To effect the changes, you need to restart network services as follows:

	/# systemctl restart network.service 

	/# ifconfig

### Activate RPMFusion Repository

There are some packages not provided by RHEL and Fedora project developers, you can find both free and nonfree packages the in RPMFusion repository, here we shall focus on free packages.

To activate it, execute the following command:
	
	/# rpm -ivh http://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-24.noarch.rpm


### Install GNOME Tweak

You can install it by simply opening the Software application and search for “GNOME tweak tool”. You will see a Install button, click on it to install.

	/# dnf install gnome-tweak-tool

### Install GNOME Shell Extensions

The GNOME shell is highly extensible, you can install additional extensions to make your system easy to configure and manage.

Simply go to the https://extensions.gnome.org/, your desktop will be detected automatically and choose the extension that you want to install by clicking on it, then use the on/off selector to activate/deactivate it.


### Install VLC Media Player

VLC is a popular, cross-platform media player that supports several video and audio formats. It can be found in the RPMFusion repository and to install it, simply run the following command:

	/# dnf install vlc


### Install Java Web Plugins

Java supports the web broadly and there are many web applications running Java code, so installing some Java web plugins will be very vital. You can issues the command below to install them:

	/# dnf install java-openjdk icedtea-web


### Install Youtube-dl – YouTube Video Downloader

Many of you have probably watched videos from YouTube.com, Facebook, Google Video and many other sites before, and to easily download your favorite videos from Youtube and some of the supported sites, you can use youtube-dl, a simple and easy to use command-line downloader.

To install it, run the command below:

	/# dnf install youtube-dl


### Install File Compression and Archiving Utilities

If you are working around Windows users, then you might have dealt with .rar and .zip compressed files several times, even possibly becoming popular on Linux.

Therefore you need to install these utilities by running the command below:

	# dnf install unzip
	
### VLC Player

There is no introduction for player, every system user known about the vlc player. we can install vlc player by using the following command

	[root@localhost ~]# dnf install vlc

### Install Spotify Music Streaming Service

If you love music like I do, then you probably want to use the best and most popular music streaming service at the moment. Although, the official Spotify client for Linux is developed for Debian/Ubuntu Linux, you can install on Fedora 24 and all the different files will be stored in the appropriate locations on your system.

First of all, add the repository from which the package will be downloaded and installed:

	/# dnf config-manager --add-repo=http://negativo17.org/repos/fedora-spotify.repo
	/# dnf install spotify-client


### Install Wine

WINE is a useful tool that enables Linux users to run Windows software directly on Linux. Though not all software is expected to work in WINE. You can install it on Fedora 24 by running the following command:

	/# dnf install wine


### Install Rufus

It is a fast image burning software for Windows but you can run it on Linux using WINE. Rufus is twice faster than some of the image burning software such as Unetbootin, Universal USB Installer plus many others probably because of its small size.

Simply download the .exe file from here: https://rufus.akeo.ie/


### Install Teamviewer

Teamviewer is a powerful remote access, support and online meeting application. It works well for those working remotely and those who need remote support on the Internet. Users can also hold online meetings, therefore helping you save time and money, making you focus on your work.

You can download teamviewer .rpm file for Fedora 24 from link https://www.teamviewer.com/en/download/linux/.

And you can install it using the RPM package manager utility as follows:

	/# rpm install /path/to/downlaod/file


### Install Different Desktops  Fedora 24

The Default desktop Environment for fedora 24 is Gnome. But many users want to use different desktops like KDE, XFCE, CINAMON, MATE, LXDE.

We can install KDE Desktop in fedora 24 by using the following command

	[root@localhost ~]# dnf install @kde-desktop

We can install MATE Desktop in fedora 24 by using the following command

	[root@localhost ~]# dnf install @mate-desktop

We can install CINNAMON Desktop in fedora 24 by using the following command

	[root@localhost ~]# dnf install @cinnamon-desktop

We can install XFCE Desktop in fedora 24 by using the following command

	[root@localhost ~]# dnf install @xfce-desktop
	
We can install LXDE Desktop in fedora 24 by using the following command

	[root@localhost ~]# dnf install @lxde-desktop

