# ubuntu-开箱配置
## 双系统时间问题
timedatectl set-local-rtc 1   
## 更换终端类型(ob-my-zsh)
sudo apt-get install git    
sudo apt-get install zsh    
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh     
chsh -s /usr/bin/zsh    
## 软件安装
### atom
download atom  [atom](https://atom.io/ "atom")     
### chrome
download chrome [chrome](https://www.chrome64bit.com/index.php/google-chrome-64-bit-for-linux "chrome")     
### emacs
sudo apt update         
sudo apt install emacs  
### virtualbox
sudo apt install virtualbox 
### deepin-wine
git clone https://github.com/HarryPotterJackson/deepin-wine-ubuntu.git    
./install.sh
### software-deepend-deepin-wine
http://mirrors.aliyun.com/deepin/pool/non-free/d/     
### vim
sudo apt update    
sudo apt install vim    
### gnome-tweak-tool
sudo apt install gnome-tweak-tool     
### popup-dict(dirctionary)
sudo apt install python3-pip   
sudo apt install python-gi python-gi-cairo python3-gi python3-gi-cairo gir1.2-gtk-3.0      
sudo pip3 install popupdict    
### gnome拓展
sudo apt install chrome-gnome-shell
### wps
download wps for linux [wps](http://community.wps.cn/download/ "wps_for_linux")   
### remarkable
download remarkable for linux [remarkable](http://remarkableapp.github.io/ "remarkable")     
### start ipv6
sudo apt install miredo    
sudo gedit /etc/default/ufw   
* change "ipv6=no" into "ipv6=yes" (maybe you should try many times )    
sudo ufw disable     
sudo ufw enable    
### lantern
download lantern [lantern](https://github.com/HarryPotterJackson/lantern "lantern for linux")   
## system language
if you install ubuntu with chinese language, you will find that the dir are "桌面 文档” etc...   
It is diffcult to chang directory.    
You can do the following:     
* change the system language into english     
* reboot    
* change the system language into chinese    
* reboot     
* at the beginning, ubuntu will remind you if you want to chang directoy name, choose "否“     
## snap
### What is snap?
**Snap** 
* is a squashFS filesystem containing your app code and a snap.yaml file containing specific metadata. It has a read-only file-system and, once installed, a writable area.      
* is self-contained. It bundles most of the libraries and runtimes it needs and can be updated and reverted without affecting the rest of the system.      
* is confined from the OS and other apps through security mechanisms, but can exchange content and functions with other snaps according to fine-grained policies controlled by the user and the OS defaults.    
snap 打包的应用不同于deb，其包含了各种依赖环境。
### snap命令
* 登陆   
   
    sudo snap login xxxxx@gmail.com    
    snap logout   
Snap 通常从 Snap Store 安装。您可以在不登录的情况下与 Snap Store 进行交互，但登录可提供许多优势。这些优势包括能够访问您的私人快照和管理快照而无需设备上的 root 。**概括来说：可以不登录，但是大部分命令就需要使用 sudo ，登录账户后则无需使用。此外登录账户后才可以发布 snap 包。**
* 查找snap包   
   
   snap find <query>    
 * 安装snap包
     
    snap install <snap>     
