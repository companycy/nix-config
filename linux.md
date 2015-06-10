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
easy_install pip
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
