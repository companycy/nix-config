curl -kL https://raw.github.com/cstrap/monaco-font/master/install-font-ubuntu.sh | bash

sudo add-apt-repository ppa:webupd8team/sublime-text-2
sudo apt-get update
sudo apt-get install -y sublime-text

# for github
ssh-keygen -t rsa -b 4096 -C "companycy@gmail.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
cat .ssh/id_rsa.pub 

# for other packages
sudo apt-get install -y emacs24 xfce4 git openssh-server subversion vagrant golang virtualbox python-setuptools vim  openjdk-7-jdk skype fcitx-table-wubi 
easy_install pip scala docker swig dpkg-dev python-dev pypy-dev python-setuptools
sudo easy_install pip

# to enable zowie kbd for ubuntu
# https://bugzilla.kernel.org/show_bug.cgi?id=46491
sudo cp /etc/modprobe.d/blacklist.conf /etc/modprobe.d/blacklist.conf.bak
vi /etc/modprobe.d/blacklist.conf
#blacklist usbkbd
sudo vi /etc/modprobe.d/blacklist.conf
sudo cp  /etc/default/grub  /etc/default/grub.bak
sudo gedit /etc/default/grub
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash usbhid.quirks=0x2345:0x0101:0x4"
sudo update-grub
sudo reboot

# for golang
export GOROOT=/usr/lib/go
export GOPATH=$HOME/go

# for salt
sudo add-apt-repository ppa:saltstack/salt
sudo apt-get update
sudo apt-get install -y salt-master salt-minion

# 
sudo rm /var/lib/apt/lists/lock

# linux_signing_key.pub to install chrome for ubuntu
sudo apt-key add linux_signing_key.pub
sudo sh -c 'echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
sudo apt-get update
sudo apt-get install google-chrome-stable


# apt-get install -y dpkg-dev
sudo apt-get install libdpkg-perl=1.17.5ubuntu5

# ubuntu 14 can't halt
sudo apt-get remove --purge bcmwl-kernel-source
sudo apt-get install linux-firmware-nonfree

# python uninstall package
sudo python setup.py install --record installed.txt
cat installed.txt | xargs sudo rm -rf

# from 163
sudo cp ~/Documents/bin/sources.list.trusty /etc/apt/sources.list

# clone branch 
git clone  -b  v0.10.0 --depth 1  https://github.com/saltstack/salt salt-0.10.0
