
Git

下载并安装 Git 
  官网: https://git-scm.com/ 
  设置环境变量,确保任意路径可以访问 git



Git 是什么？  
Git是目前世界上最先进的分布式版本控制系统
Git特点：高端大气上档次

Linus - 1991 开源了 Linux - 服务器系统
        2002 本人合并代码
        反对使用CVS SVN版本控制系统 - 集中式/速度慢/联网
        2002 商业版本控制系统 BitKeeper
        2005 牛人Andrew 破解 BitKeeper
Linus - 两周时间 C - 分布式版本控制系统 Git    
        2008 GitHub - 开源项目免费提供 Git 存储
             GitLab - 码云 

集中式版本控制系统:
CVS SVN版本控制系统 - 集中式/速度慢/联网 

分布式版本控制系统:
Git - 分布式/本地库/远程库-联网/速度快   


检查Git安装环境:
cmd     : git --version
Git Bash: git --version   
$ git 显示git操作的所有命令   

$ git config --list 查看配置信息

未配置则输入以下三行代码 
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
$ git config --global credential.helper wincred  

新建Git项目:
step 1:
切换windows下盘符
$ cd /d --------- 切换到 D:\
$ mkdir gitdemo --------- 新建文件夹(目录)   
$ cd gitdemo ----------- 进入子目录
$ pwd ------------ 显示完整路径

step 2:
把当前目录 D:\gitdemo 初始化为Git可以管理的仓库(repository)
$ git init  -------初始化空的仓库  empty Git repository
$ ls -ah ---------- 显示隐藏文件

把一个文件放到Git仓库
$ git add readme.tx --------- 把文本添加到仓库
$ git commit -m "wrote a readme file" ----把文件提交到仓库

$ git add note1.txt
$ git add note2.txt note3.txt
$ git commit -m "add 3 note file"

$ git add notes ---- 添加文件夹
$ git commit -m "add notes folder"

$ git status ----- 查看工作区的状态

$ git diff readme.txt ----- 查看文件修改的内容

$ git log 查看历史记录

:q -- 退出查看历史记录

历史记录一行显示一条历史记录
$ git log --pretty=oneline

Git的SHA1计算出来的版本号commit id
f06cc1877ad5da69833520dc5ec9f1a0f7bddb40
非常大的数字;用十六进制表示



时光穿梭机 - 月光宝盒 - 回到五百年前

回到上一个版本
git reset --hard HEAD^
git reset --hard HEAD~1

上上一个版本: HEAD^^
往上100个版本: HEAD~100

回到未来的版本
git reset --hard commit_id[前7为字符]

git reflog 查看命令历史



工作区和暂存区
工作区Working Directory: 当前目录gitdemo

版本库Repository:
工作区有一个隐藏目录.git--不算工作区,是版本库

暂存区stage



撤销修改
写了乱代码,未git add
git status
git checkout -- readme.txt 丢弃工作区的修改
恢复到修改之前的状态

写了乱代码,且git add
git add readme.txt
git status
git reset HEAD readme.txt --重置到主分支版本
git status
git checkout -- readme.txt 丢弃工作区的修改
git status

写了乱代码,且git add --> git commit
等着挨批



删除文件
rm note1.txt ------ 删除工作区的文件
git rm note1.txt ---- 从版本库删除文件

rm note1.txt ------ 删除工作区的文件
删除文件错了,恢复工作区的文件
git checkout -- note1.txt



远程仓库:
在本地仓库
git init
git add xxx.txt xxx.java
git commit -m "first commit"

推送到远程
git remote add origin https://github.com/用户名username/仓库名repository.git
git push -u origin master
