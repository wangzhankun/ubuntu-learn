# [教程网址](https://git-scm.com/book/zh/v1/%E8%B5%B7%E6%AD%A5-Git-%E5%9F%BA%E7%A1%80)
# [版本控制](https://git-scm.com/book/zh/v1/%E8%B5%B7%E6%AD%A5-%E5%85%B3%E4%BA%8E%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6)
# [Git思想与基本原理](https://git-scm.com/book/zh/v1/%E8%B5%B7%E6%AD%A5-Git-%E5%9F%BA%E7%A1%80)
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

# 记录每次更新到仓库[website](https://git-scm.com/book/zh/v1/Git-%E5%9F%BA%E7%A1%80-%E8%AE%B0%E5%BD%95%E6%AF%8F%E6%AC%A1%E6%9B%B4%E6%96%B0%E5%88%B0%E4%BB%93%E5%BA%93)

# 查看提交历史[website](https://git-scm.com/book/zh/v1/Git-%E5%9F%BA%E7%A1%80-%E6%9F%A5%E7%9C%8B%E6%8F%90%E4%BA%A4%E5%8E%86%E5%8F%B2)
git log    
git log -p:展开显示每次提交的内容差异     
git log -p -number:展开显示每次提交的内容差异；number表示显示最近number次的更改。       
git log -U1 --word-diff：-U1表示上下文行数为一行；被删除的单词被【--】包括；被增加的单词被{++}包括。      
git log --graph:显示 ASCII 图形表示的分支合并历史。   

# 撤销操作[website](https://git-scm.com/book/zh/v1/Git-%E5%9F%BA%E7%A1%80-%E6%92%A4%E6%B6%88%E6%93%8D%E4%BD%9C) 
**请注意，有些撤销操作是不可逆的，所以请务必谨慎小心.**    
git commit --amend:撤消刚才的提交(commit)操作.    

# 远程仓库使用[website](https://git-scm.com/book/zh/v1/Git-%E5%9F%BA%E7%A1%80-%E8%BF%9C%E7%A8%8B%E4%BB%93%E5%BA%93%E7%9A%84%E4%BD%BF%E7%94%A8)
## 查看当前远程库
至少可以看到一个名为 origin 的远程库，Git 默认使用这个名字来标识你所克隆的原始仓库。       
git remote -v:列出远程仓库和对应克隆网址     
## 添加远程仓库
git remote add [name] [url]：添加一个新的远程仓库，并指定一个简单的名字，以便将来引用。    
上述命令只是添加一个仓库，并没有内容。增加内容执行下列命令：     
git fetch [name]
## 从远程仓库抓取数据
git fetch [name]    
**fetch 命令只是将远端的数据拉到本地仓库，并不自动合并到当前工作分支，只有当你确实准备好了，才能手工合并。**      
此命令会到远程仓库中拉取所有你本地仓库中还没有的数据。运行完成后，你就可以在本地访问该远程仓库中的所有分支，将其中某个分支合并到本地，或者只是取出某个分支，一探究竟。      
实际上，默认情况下 git clone 命令本质上就是自动创建了本地的 master 分支用于跟踪远程仓库中的 master 分支（假设远程仓库确实有 master 分支）。所以一般我们运行 git pull，目的都是要从原始克隆的远端仓库中抓取数据后，合并到工作目录中的当前分支。       
## 推送数据到远程仓库
git push [remote-name] [branch-name]    
**再次说明下，克隆操作会自动使用默认的 master 和 origin 名字**      
## 远程仓库的删除和重命名
git remote rename [old-name] [new-name]  
git remote rm [remote-name]    

# 标签[website](https://git-scm.com/book/zh/v1/Git-%E5%9F%BA%E7%A1%80-%E6%89%93%E6%A0%87%E7%AD%BE)
## 查看标签
git tag:显示所有标签。                      
git tag -l 'TAG':显示所有与标签TAG相关的tag。     
例如：   
$ git tag -l 'v1.4.2.\*'     
v1.4.2.1    
v1.4.2.2    
v1.4.2.3    
v1.4.2.4    
git show [tag] :显示tag的标签信息。    
## 创建标签
git tag -a [tag] -m 'annotated':标签名称和附注     
## 签署标签
## 验证标签
## 分享标签
默认情况下，git push 并不会把标签传送到远端服务器上    
git push [remote-name] [tagname]：share对应tagname的标签    
如果要一次推送所有本地新增的标签上去    
git push [remote-name] --tags

# Git技巧[website](https://git-scm.com/book/zh/v1/Git-%E5%9F%BA%E7%A1%80-%E6%8A%80%E5%B7%A7%E5%92%8C%E7%AA%8D%E9%97%A8)
## 自动补全
## Git命令别名
