# ubuntu-开箱配置


### change mirror
配置文件在`/etc/apt/sources.list`，可以将原配置文件修改为:这里是使用的清华的源。（注意，将原文件内容删除）

```Bash
  # 这里的是18.04的镜像需要根据不同版本进行选择
  # 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
  # 预发布软件源，不建议启用
  # deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
```
### start ipv6

```Bash
sudo apt install miredo    
sudo gedit /etc/default/ufw   
```

* change "ipv6=no" into "ipv6=yes" (maybe you should try many times )    
sudo ufw disable     
sudo ufw enable    
### 双系统时间问题
timedatectl set-local-rtc 1   
### 更换终端类型(oh-my-zsh)

```Bash
sudo apt install zsh  curl git
chsh -s /bin/zsh  
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"    
sudo apt install autojump
 vim ~/.zshrc
        plugins=(git autojump)
```

### vscode

download [vscode](https://code.visualstudio.com/)

### chrome
download chrome [chrome](https://www.chrome64bit.com/index.php/google-chrome-64-bit-for-linux "chrome")     
### vim
sudo apt update    
sudo apt install vim    
### gnome-tweak-tool
sudo apt install gnome-tweak-tool     
### gnome拓展
sudo apt install chrome-gnome-shell
### wps
download wps for linux [wps](http://community.wps.cn/download/ "wps_for_linux")   
### zeal
sudo apt install zeal     
### gitkraken
https://www.gitkraken.com/
### lantern
download lantern [lantern](https://github.com/HarryPotterJackson/lantern "lantern for linux")    
### chinese input
sudo apt install fcitx     
https://pinyin.sogou.com/linux/?r=pinyin       

## ROS安装

在安装源部分需要区分版本，这里提供了16.04和18.04两个安装版本。

### ubuntu 16.04

这是ubuntu16.04版本的ros安装教程，不适用其他版本。

```Bash
 
sudo vim /etc/apt/sources.list  #修改镜像文件
```
```Bash

# 这里的内容是针对ubuntu16.04，其他版本不适用
#将这里的所有信息直接复制粘贴即可，先删除原文件中的所有内容
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security main restricted universe multiverse
# 预发布软件源，不建议启用

# deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-proposed main restricted universe multiverse

# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-proposed main restricted universe multiverse

# 默认注释了源码仓库，如有需要可自行取消注释

deb https://mirrors.ustc.edu.cn/ubuntu/ xenial main restricted universe multiverse

# deb-src https://mirrors.ustc.edu.cn/ubuntu/ xenial main restricted universe multiverse

deb https://mirrors.ustc.edu.cn/ubuntu/ xenial-updates main restricted universe multiverse

# deb-src https://mirrors.ustc.edu.cn/ubuntu/ xenial-updates main restricted universe multiverse

deb https://mirrors.ustc.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse

# deb-src https://mirrors.ustc.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse

deb https://mirrors.ustc.edu.cn/ubuntu/ xenial-security main restricted universe multiverse

# deb-src https://mirrors.ustc.edu.cn/ubuntu/ xenial-security main restricted universe multiverse

# 预发布软件源，不建议启用

# deb https://mirrors.ustc.edu.cn/ubuntu/ xenial-proposed main restricted universe multiverse

# deb-src https://mirrors.ustc.edu.cn/ubuntu/ xenial-proposed main restricted universe multiverse
```

```bash

sudo sh -c '. /etc/lsb-release && echo "deb http://mirrors.ustc.edu.cn/ros/ubuntu/ $DISTRIB_CODENAME main" > /etc/apt/sources.list.d/ros-latest.list'    

sudo sh -c '. /etc/lsb-release && echo "deb https://mirrors.tuna.tsinghua.edu.cn/ros/ubuntu/ $DISTRIB_CODENAME main" >> /etc/apt/sources.list.d/ros-latest.list'  

sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654    

sudo apt-get update && sudo apt upgrade    

sudo apt-get install ros-kinetic-desktop-full    
```


### Ubuntu 18.04

```Bash
# 这里的是18.04的镜像需要根据不同版本进行选择
  # 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
  # 预发布软件源，不建议启用
  # deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
```

```bash
sudo sh -c 'echo "deb https://mirrors.tuna.tsinghua.edu.cn/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

sudo apt update

sudo apt install ros-melodic-desktop-full
```





### Initialize rosdep

在这一步的update命令上可能会由于网络原因多次失败，重复命令即可，直到成功。
```Bash
sudo rosdep init    
rosdep update
```
### Environment setup
更改过终端的要把下面的内容进行对应更改。不知道啥是终端更改的忽略这句话。
```Bash
echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
我更改了终端为zsh，因此命令修改如下
```
echo "source /opt/ros/kinetic/setup.zsh" >> ~/.zshrc
source ~/.zshrc
```
### Dependencies for building packages
```
sudo apt install python-rosinstall python-rosinstall-generator python-wstool build-essential
```
### 启动ROS
```
roscore
```
启动成功即可。最后使用Ctrl+c 退出ROS系统。



