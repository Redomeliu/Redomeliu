# 前言🐱‍🚀

本项目为本人学习阶段的一些成果与联系
我是热爱技术但常常出bug的莫语😬

学习许久发现都在进行无效学习，无论学了什么都没有一个真正的知识体系。

付出很多，但收获很小努力很久，但却越发迷茫。

为此，我将重新梳理知识重点，以此文档为准

# 目录

### [git](#git)

### [c++](#c++)

### [python](#python)

























# git

## git目录

### [git仓库初始化](仓库初始化)

## git clone

```bash
$ git clone <仓库地址> <自定义文件夹名称>
```

```bash
git clone git@github.com:fsliurujie/test.git      --SSH协议
git clone git://github.com/fsliurujie/test.git    --GIT协议
git clone https://github.com/fsliurujie/test.git  --HTTPS协议
```

## git仓库初始化

使用当前目录作为Git仓库，我们只需使它初始化。

```bash
git init
```

该命令执行完后会在当前目录生成一个 .git 目录。

使用我们指定目录作为Git仓库。

```bash
git init newrepo
```

## 文件添加

```bash
$ git add *.c
$ git add README.md//添加文件在暂存区
$ git commit -m '初始化项目版本'//将提交到仓库，并且说明
```

## 文件创建

```bash
#git命令创建文件
touch readme.txt
```

## git配置

显示配置列表

```bash
 git config --list
```

编辑配置文件

```bash
$ git config -e    # 针对当前仓库 
```

```bash
$ git config -e --global   # 针对系统上所有仓库
```

修改提交者信息

```bash
$ git config --global user.name "runoob"
$ git config --global user.email test@runoob.com
```

## 版本控制：

### 查看版本：

```bash
1.git log 					#查看历史所有版本信息
2.git log -x 				#查看最新的x个版本信息
3.git log -x filename
#查看某个文件filename最新的x个版本信息（需要进入该文件所在目录)
4.git log --pretty=oneline
#查看历史所有版本信息，只包含版本号和记录描述
```



### 回滚版本：

```bash
1.git reset --hard HEAD^  			回滚到上个版本

2.git reset --hard HEAD^~2			回滚到前两个版本

3.git reset --hard xxx(版本号或版本号前几位)
回滚到指定版本号，如果是版本号前几位，git会自动寻找匹配的版本号

4.git reset --hard xxx(版本号或版本号前几位) filename
回滚某个文件到指定版本号（需要进入该文件所在目录）
```

删除某个曾经提交的commit：

##### git rebase

- `git rebase`：当两个分支不在一条线上，需要执行 merge 操作时使用该命令。

1. 撤销提交
   如果中间的某次 commit 需要删除，可以通过 `git rebase` 命令实现，方法如下：

```go
1. git log // 查找要删除的前一次提交的 commit_id
2. git rebase -i commit_id // 将 commit_id 替换成复制的值
3. 进入 Vim 编辑模式，将要删除的 commit 前面的 `pick` 改成 `drop`
4. 保存并退出 Vim
```

## 常用命令：

### 提交与修改

Git 的工作就是创建和保存你的项目的快照及与之后的快照进行对比。

下表列出了有关创建与提交你的项目的快照的命令：

| 命令         | 说明                                     |
| :----------- | :--------------------------------------- |
| `git add`    | 添加文件到仓库                           |
| `git status` | 查看仓库当前的状态，显示有变更的文件。   |
| `git diff`   | 比较文件的不同，即暂存区和工作区的差异。 |
| `git commit` | 提交暂存区到本地仓库。                   |
| `git reset`  | 回退版本。                               |
| `git rm`     | 删除工作区文件。                         |
| `git mv`     | 移动或重命名工作区文件。                 |

### 提交日志

| 命令               | 说明                                 |
| :----------------- | :----------------------------------- |
| `git log`          | 查看历史提交记录                     |
| `git blame <file>` | 以列表形式查看指定文件的历史修改记录 |

### 远程操作

| 命令         | 说明               |
| :----------- | :----------------- |
| `git remote` | 远程仓库操作       |
| `git fetch`  | 从远程获取代码库   |
| `git pull`   | 下载远程代码并合并 |
| `git push`   | 上传远程代码并合并 |

SSH生成(与服务器或github链接)

```c++
ssh-keygen -t rsa -C "xxxxx@qq.com"
```

windows生成于User下的用户名所在目录的.ssh文件夹中

私钥用于客户端

公钥为服务器.pub

### Git与GitHub连接

git push -f origin master 强行推送，覆盖所有

```bash
git init
git remote add origin https://github.com/hyinli/teach.git
git pull -f origin master
#添加源
git add .
git commit -m "your descprition(自己定义)"
git push -u origin master
git checkout -b gh-pages
git add .
git commit -m "the 2nd"
git push origin gh-pages
```

```bash
git remote add origin git@github.com:Redomeliu/huba_tools.git
git branch -M main
git push -u origin main
```

