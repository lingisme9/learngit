# Git 的基本使用：

##  ubandtu下使用git：

1.**安装**：`sudo apt-get install git`

**2.配置git**
	1.`git config --global user.name “github昵称”`

​	2.`git config --global user.email “github邮箱”`

**3.创建验证访问的公匙**

​	1.`ssh-keygen -C 'github email' -t rsa`,一路下一步不设置密码，也可以设置

**4.复制公匙**

​	1.`cd ～/.ssh`

​	2.`gedit id_rsa.pub`

​	3.github添加公匙

**5.测试连接**

​	1.`ssh -T git@github.com`



**本地仓库使用**



1.`git init `初始化本地仓库

2.`git add filename` ：提交文件到缓存区

3.`git commit -m “描述提交了啥”`

4.**绑定远程仓库**

​	1.新建远程仓库，连readme都不要有

​	2.`git remote add origin（远程仓库名：啥都可见名知义）仓库地址（git）`

​	3.`git push -u origin master`：推送本地仓库到远程库上

​	4.只要做了本地提交就可以，`git push origin master`

5.**删除文件**

​	一般情况下，你通常直接在文件管理器中把没用的文件删了，或者用`rm`命令删了：

```
$ rm test.txt
```

这个时候，Git知道你删除了文件，因此，工作区和版本库就不一致了，`git status`命令会立刻告诉你哪些文件被删除了：

```
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	deleted:    test.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

现在你有两个选择，一是确实要从版本库中删除该文件，那就用命令`git rm`删掉，并且`git commit`：

```
$ git rm test.txt
rm 'test.txt'

$ git commit -m "remove test.txt"
[master d46f35e] remove test.txt
 1 file changed, 1 deletion(-)
 delete mode 100644 test.txt
```

现在，文件就从版本库中被删除了。然后push本地仓库



另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本：

```
$ git checkout -- test.txt
```

`git checkout`其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。