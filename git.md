# 教程网址https://git-scm.com/book/zh/v1/%E8%B5%B7%E6%AD%A5-Git-%E5%9F%BA%E7%A1%80

# 要养成一开始就创建.gitignore文件的习惯      
******************************************************************************************
# 获取帮助
$ git help <verb>    
$ git <verb> --help    
$ man git-<verb>    

# 忽略某些文件
在Git工作区的根目录下创建一个特殊的.gitignore文件，然后把要忽略的文件名填进去，Git就会自动忽略这些文件。     
不需要从头写.gitignore文件，GitHub已经为我们准备了各种配置文件，只需要组合一下就可以使用了。所有配置文件可以直接在线浏览：https://github.com/github/gitignore       

### 忽略文件的原则是：
   
   1.忽略操作系统自动生成的文件，比如缩略图等；    
   2.忽略编译生成的中间文件、可执行文件等，也就是如果一个文件是通过另一个文件自动生成的，那自动生成的文件就没必要放进版本库，比如Java编译产生的.class文件；     
   3.忽略你自己的带有敏感信息的配置文件，比如存放口令的配置文件。      
   
### 忽略文件的写法
#### 经测试发现，若要忽略一个文件夹下的部分文件夹，应该一个一个的标示。可能有更好的方法。      
若test下有多个文件和文件夹。若要ignore某些文件夹，应该这样配置.gitignore文件。若test下有test1，test2,test3文件。要track test3，则.gitignore文件为：         
test/test1   
test/test2   
!test/test3   
若为：   
test/   
!test/test3 ，则不能track test3。    
#### Git 中的文件忽略
   
   1. 共享式忽略新建 .gitignore 文件，放在工程目录任意位置即可。.gitignore 文件可以忽略自己。忽略的文件，只针对未跟踪文件有效，对已加入版本库的文件无效。   
   2. 独享式忽略针对具体版本库 ：.git/info/exclude针对本地全局：  git config --global core.excludefile ~/.gitignore    
#### 忽略的语法规则：     
(#)表示注释           
(*)  表示任意多个字符;       
(?) 代表一个字符;           
 ([abc]) 代表可选字符范围                                
如果名称最前面是路径分隔符 (/) ，表示忽略的该文件在此目录下。             
如果名称的最后面是 (/) ，表示忽略整个目录，但同名文件不忽略。             
通过在名称前面加 (!) ，代表不忽略。               
例子如下：           
\# 这行是注释                                         
*.a                   # 忽略所有 .a 伟扩展名的文件                             
!lib.a                # 但是 lib.a 不忽略，即时之前设置了忽略所有的 .a                     
/TODO                 # 只忽略此目录下 TODO 文件，子目录的 TODO 不忽略                   
build/               # 忽略所有的 build/ 目录下文件                                  
doc/*.txt           # 忽略如 doc/notes.txt, 但是不忽略如 doc/server/arch.txt                          
