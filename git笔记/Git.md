Git
===
Git简介
---

Git 是一个开源的**分布式版本控制系统**，是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件   
版本控制是一种记录文件内容变化，已方便将来查阅特定版本修订    
**集中化版本控制系统**是将所以文件和文件的修订版本放置与单一集中管理的服务器，所以协同工作的人都通过客户端连接这台服务器，取出最新的文件或者更改提交  
**分布式版本控制系统**的客户端会把代码完整的从远程仓库克隆下来，在本地仓库操作，每一次克隆都是对代码仓库完整的备份  
**分布式的好处：**  
1. 工作时不需要联网  
2. 更加安全  

Git配置  
---

Git 提供了一个叫做 git config 的工具，专门用来配置或读取相应的工作环境变量  

/etc/gitconfig 文件：系统中对所有用户都普遍适用的配置  
* 使用```git config --system```读取的是/etc/gitconfig 文件  

~/.gitconfig 文件：用户目录下的配置文件只适用于该用户  
* 使用```git config --global```读取的是~/.gitconfig 文件  

当前项目的 Git 目录中的配置文件（也就是工作目录中的 .git/config 文件）  
* 配置仅仅针对当前项目有效（每一个级别的配置都会覆盖上层的相同配置，所以 .git/config 里的配置会覆盖 /etc/gitconfig 中的同名变量）

配置用户名和邮箱：
```js
git config --global user.name "youName"
git config --global user.email testYouEmail@163.com
```
用了 --global 选项，那么更改的配置文件就是位于你用户主目录下的那个，以后你所有的项目都会默认使用这里配置的用户信息  
要在某个特定的项目中使用其他名字或者电子邮件，只要去掉 --global 选项重新配置即可，新的设定保存在当前项目的 .git/config 文件里  

查看配置信息：
```jsj
git config --list
```
可以直接查阅某个环境变量的设定   
```js
git config user-email
```  
检查版本  
```js
git --version
```

Git 创建仓库  
---
git init （指定目录）  初始化Git仓库（生成一个.git的目录文件），没有指定就是当前目录
```js
git init//当前目录初始化
git init LearnGit//指定LearnGit目录并初始化
```
初始化后，会目录下会生成一个名为.git 的目录，所有Git需要的数据和资源都存放在这个目录中  

git add (文件名)(文件名) 用于增加文件纳入暂存区，可以同时添加多个文件，     
```js
git add .//将添加全部文件到暂存区
git add *.jsx//将以.jsx结尾的文件加入暂存区
git add LearnGitExample//将LearnGitExample文件纳入暂存区 
```

git clone
```js
git clone repo //克隆到当前目录
git clone repo directory //克隆到指定目录
```

Git 分支管理
```js
git branch//列出所有本地分支
git branch branchname//创建分支
git checkout branchname//切换分支
git merge branchname//合并分支到当前分支
git branch -d branchname//删除分支
```

Git 查看提交历史
```js
git log //查看历史提交记录
git log --oneline  //查看历史记录的简洁的版本
git log --reverse --oneline //查看历史记录,逆向显示所有日志的简洁的版本
git blame <file> // 以列表形式查看指定文件的历史修改记录
```

Git 标签
```js
git tag -a v1.0 //执行git tag -a 命令时，Git会打开你的编辑器，可以写一句标签注解
```

Git 远程仓库(Github)
```js
git remote//查看当前的远程库
git remote -v//加上 -v 参数可以看到每个别名的实际链接地址
```

Git命令基础
===
基础命令
---


3. git commit -m '提交说明' __提交暂存区到本地仓库，提交说明Windows系统使用双引号，Linux系统使用单引号__  
4. git clone （文件位置） （指定名称（可选））**拷贝现有的仓库，没有指定位置的时候默认当前位置**
5. git config --list **查看配置文件**  
    > git config -e     针对当前仓库配置  
    > git config -global 针对系统上所有仓库  
6. git status **检查上次提交后是否有修改**  
7. git diff **比较文件在暂存区和工作区的差异**  
8. git push  <远程主机名> <本地分支名>:<远程分支名> **将本地的分支版本上传到远程并合并**  
9. git pull <远程主机名> <远程分支名>:<本地分支名> **从远程获取代码并合并本地的版本**
10. git log 查看提交记录
11. git reset （） 回退到（）版本