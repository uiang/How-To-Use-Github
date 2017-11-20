## 使用GitHub的前期准备

### 几个重要的使用前准备

* 设置 SSH Key
* 添加公开密钥：使用私人密钥与 GitHub 进行认证和通信

### 直接在网页中创建仓库

* 帮我们把不需要在 Git 仓库中进行版本管理的文件记录在 .gitignore 文件中。
* license 许可协议文件
* README.md 一般会在这个文件中标明本仓库所包含的软件的概要、使用流程、许可协议等信息。

### 公开代码

* clone 已有仓库

尝试在已有仓库中添加代码并加以公开。首先将已有仓库 clone 带身边的开发环境中。将仓库作为一个文件夹 clone 到计算机当前路径中。
```
tangruideMacBook-Pro:GitHub loisdawn$ git clone https://github.com/uiang/How-To-Use-Github.git
Cloning into 'How-To-Use-Github'...
remote: Counting objects: 18, done.
remote: Compressing objects: 100% (14/14), done.
remote: Total 18 (delta 2), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (18/18), done.
```
```
tangruideMacBook-Pro:GitHub loisdawn$ cd How-To-Use-Github
```
```
tangruideMacBook-Pro:How-To-Use-Github loisdawn$ ls
README.md			chapter-02-Git.md
chapter-01-introduction.md	hello_world.php
```
```
tangruideMacBook-Pro:How-To-Use-Github loisdawn$ git status
 On branch master
 Your branch is up-to-date with 'origin/master'.
 Untracked files:
   (use "git add <file>..." to include in what will be committed)
 ​	hello_world.php
 nothing added to commit but untracked files present (use "git add" to track)
```
* 编写代码

```php
# hello_world.php
<?php
	echo "Hello World";
?>
```
* 提交

将 hello_world.php 提交至仓库使得文件进入了版本管理系统的管理之下。今后的更改都交由 Git 进行。
```
tangruideMacBook-Pro:How-To-Use-Github loisdawn$ git add hello_world.php
```
```
tangruideMacBook-Pro:How-To-Use-Github loisdawn$ git commit -m "Add hello world script by php"
[master f4af23c] Add hello world script by php
  1 file changed, 3 insertions(+)
  create mode 100644 hello_world.php
```
通过 git add 命令将文件加入暂缓区（在 Index 数据结构中记录文件提交之前的状态），在通过 git commit 命令提交。

添加成功后，可以通过 git log 命令查看提交日志。
```
tangruideMacBook-Pro:How-To-Use-Github loisdawn$ git log
 commit f4af23c12ee8c6f5770ea9d880aa4b8353db9dbb (**HEAD -> ****master**)
 Author: Rui Tang <tang.rui.study@gmail.com>
 Date:   Mon Nov 20 22:23:25 2017 +0100
 ​    Add hello world script by php
 
 commit 87d29d66bd948bb74b16eac4fcda5e8559861b1b (**origin/master**, **origin/HEAD**)
 Author: uiang <tang.rui.study@gmail.com>
 Date:   Sun Nov 19 23:47:04 2017 +0100
 ​    Update chapter-02-Git.md
 
 commit 34e7730aab9e5af7da4a2f0988417a66fc257998
 Author: uiang <tang.rui.study@gmail.com>
 Date:   Sun Nov 19 23:35:18 2017 +0100
 ​    Create chapter-02-Git.md
 
 commit b989b0d7766926d1dc272893382d3c3efd32c232
 Author: uiang <tang.rui.study@gmail.com>
 Date:   Sun Nov 19 23:32:47 2017 +0100
 ​    Update README.md
```
* 进行 push

之后只要执行 push，GitHub 上的仓库就会被更新。
```
tangruideMacBook-Pro:How-To-Use-Github loisdawn$ git push
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 323 bytes | 323.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/uiang/How-To-Use-Github.git
   87d29d6..f4af23c  master -> master
```
