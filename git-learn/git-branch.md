# linux filesystem[鸟哥的linux私房菜](http://linux.vbird.org/linux_basic/0230filesystem.php)
# 文件系统快照 [华为support](http://support.huawei.com/enterprise/docinforeader!loadDocument1.action?contentId=DOC1000053469&partNo=10062#os_snapshotfea_desc)
# Git 分支——何谓分支[website](https://git-scm.com/book/zh/v1/Git-%E5%88%86%E6%94%AF-%E4%BD%95%E8%B0%93%E5%88%86%E6%94%AF)
## 分支创建
git branch [branch_name]    
## 分支切换
git checkout [branch_name]    
## 分支查看
git log --oneline --decorate --graph --all   
**git checkout -b [branch_name] 等价git branch [branch_name]&&git checkout [branch_name]**      
## 删除branch
git branch -d [branch_name]   
## git 分支的新建与合并[website](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%88%86%E6%94%AF%E7%9A%84%E6%96%B0%E5%BB%BA%E4%B8%8E%E5%90%88%E5%B9%B6)
## git 分支管理[website](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%88%86%E6%94%AF%E7%AE%A1%E7%90%86)
## git分支开发工作流[website](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%88%86%E6%94%AF%E5%BC%80%E5%8F%91%E5%B7%A5%E4%BD%9C%E6%B5%81)
## git 远程分支[website](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E8%BF%9C%E7%A8%8B%E5%88%86%E6%94%AF)
远程引用是对远程仓库的引用（指针），包括分支、标签等等。 你可以通过 git ls-remote (remote) 来显式地获得远程引用的完整列表，或者通过 git remote show (remote) 获得远程分支的更多信息。 然而，一个更常见的做法是利用远程跟踪分支。    
### 推送
### 跟踪分支
# 重要变基[website](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%8F%98%E5%9F%BA)

