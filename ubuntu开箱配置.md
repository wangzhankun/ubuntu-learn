# ubuntu-开箱配置
## 系统设置
### system language
if you install ubuntu with chinese language, you will find that the dir are "桌面 文档” etc...   
It is diffcult to chang directory.    
You can do the following:     
* change the system language into english     
* reboot    
* change the system language into chinese    
* reboot     
* at the beginning, ubuntu will remind you if you want to chang directoy name, choose "否“    
### start ipv6
sudo apt install miredo    
sudo gedit /etc/default/ufw   
* change "ipv6=no" into "ipv6=yes" (maybe you should try many times )    
sudo ufw disable     
sudo ufw enable    
### 双系统时间问题
timedatectl set-local-rtc 1   
### 更换终端类型(ob-my-zsh)
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
### zeal
sudo apt install zeal     
### gitkraken
https://www.gitkraken.com/
### lantern
download lantern [lantern](https://github.com/HarryPotterJackson/lantern "lantern for linux")  
