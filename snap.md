# snap
## What is snap?
**Snap** 
* is a squashFS filesystem containing your app code and a snap.yaml file containing specific metadata. It has a read-only file-system and, once installed, a writable area.      
* is self-contained. It bundles most of the libraries and runtimes it needs and can be updated and reverted without affecting the rest of the system.      
* is confined from the OS and other apps through security mechanisms, but can exchange content and functions with other snaps according to fine-grained policies controlled by the user and the OS defaults.    
snap 打包的应用不同于deb，其包含了各种依赖环境。
## snap命令
* 登陆   
   
    sudo snap login xxxxx@gmail.com    
    snap logout   
Snap 通常从 Snap Store 安装。您可以在不登录的情况下与 Snap Store 进行交互，但登录可提供许多优势。这些优势包括能够访问您的私人快照和管理快照而无需设备上的 root 。**概括来说：可以不登录，但是大部分命令就需要使用 sudo ，登录账户后则无需使用。此外登录账户后才可以发布 snap 包。**
* 查找snap包   
   
   snap find \<query>    
 * 安装snap包
     
    snap install \<snap>     
