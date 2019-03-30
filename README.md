# git基本操作

## 客户端安装

[官网下载git客户端](https://git-scm.com/downloads) 并完成安装，详细过程不再赘述！

启动 Git Bash 检验。

命令：**git** 或者 **git --version**

```shell
wj@localhost MINGW64 /d
$ git --version
git version 2.20.1.windows.1
```

## git 用户信息配置

1. 配置用户信息

   命令：**git config --global user.name "你的名字"**

   ​            **git config --global user.email "你的邮箱"**

   ```shell
   wj@localhost MINGW64 /d
   $ git config --global user.name "wangjun"
   
   wj@localhost MINGW64 /d
   $ git config --global user.email "wangjun9406@163.com"
   ```

   

2. 查看配置信息

   命令：**git config --global user.name**

   ​	    **git config --global user.email**

   ```shell
   wj@localhost MINGW64 /d
   $ git config --global user.name
   wangjun
   
   wj@localhost MINGW64 /d
   $ git config --global user.email
   wangjun9406@163.com
   ```

   

3. 修改配置信息并查看

   ```shell
   wj@localhost MINGW64 /d
   $ git config --global user.name "wj"
   
   wj@localhost MINGW64 /d
   $ git config --global user.name
   wj
   
   wj@localhost MINGW64 /d
   $ git config --global user.email "2370959316@qq.com"
   
   wj@localhost MINGW64 /d
   $ git config --global user.email
   2370959316@qq.com
   ```

   

## 创建本地库并初始化

命令：**git init**

```shell
wj@localhost MINGW64 /d
$ cd workspace/

wj@localhost MINGW64 /d/workspace
$ mkdir git-learning

wj@localhost MINGW64 /d/workspace
$ cd git-learning/

wj@localhost MINGW64 /d/workspace/git-learning
$ git init
Initialized empty Git repository in D:/workspace/git-learning/.git/
```



## 添加文件至缓存区

主要命令(添加文件至缓存区)：**git add yourfile**

辅助命令(查看当前仓库/分支状态)：**git status**

```shell
wj@localhost MINGW64 /d/workspace/git-learning (master)
$ touch README.md

wj@localhost MINGW64 /d/workspace/git-learning (master)
$ vim README.md

wj@localhost MINGW64 /d/workspace/git-learning (master)
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        README.md

nothing added to commit but untracked files present (use "git add" to track)

wj@localhost MINGW64 /d/workspace/git-learning (master)
$ git add README.md

wj@localhost MINGW64 /d/workspace/git-learning (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   README.md
```



## 提交缓存区文件至本地库

命令：**git commit -m "本次提交说明"**

```shell
wj@localhost MINGW64 /d/workspace/git-learning (master)
$ git commit -m "add README.md file"
[master (root-commit) 0fd2779] add README.md file
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

wj@localhost MINGW64 /d/workspace/git-learning (master)
$ git status
On branch master
nothing to commit, working tree clean
```



## 本地库与远程库同步

命令：**git remote add origin 仓库地址**

```shell
wj@localhost MINGW64 /d/workspace/git-learning (master)
$ git remote add origin https://github.com/bearPotMan/git-learning.git
```



## 推送本地库内容至远程库

命令：**git push -u origin master**

```shell
wj@localhost MINGW64 /d/workspace/git-learning (master)
$ git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 252 bytes | 252.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/bearPotMan/git-learning.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

```



以上就是最基本的第一次记录提交！



之后的文件的修改与提交使用的命令主要有三个：

- git add file
- git commit -m "本次提交说明"
- git push -u origin master



# git 常用命令

- **git status**：查看当前仓库/分支文件提交状态

- **git checkout -- file**：撤销工作区的修改，在下一次 **add** 操作之前执行该命令才有效

- **git add file**：添加文件至缓存区

- **git reset HEAD file**：撤销缓存区的修改

- **git commit -m "本次提交说明"**：提交缓存区文件至本地仓库

- **git push -u origin master**：推送本地仓库内容至远程仓库 master 分支

- **git branch**：查看当前分支

- **git branch dev**：创建 dev 分支

- **git checkout dev**：切换至 dev 分支

- **git log**：查看提交历史记录

- **git reflog**：查看命令历史记录

- **git clone https://github.com/bearPotMan/git-learn**：克隆仓库

- **git pull origin master:dev**：将远程 master 分支拉取到本地 dev 分支

  ...

其他命令后续用的比较熟练了再更新吧！