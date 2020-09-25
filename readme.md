# Git 的基本使用：

##  ubandtu下使用git：

**1.安装**：`sudo apt-get install git`

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

4.绑定远程仓库

​	1.新建远程仓库，连readme都不要有

​	2.`git remote add origin（远程仓库名：啥都可见名知义）仓库地址（git）`

​	3.`git push -u origin master`：推送本地仓库到远程库上

​	4.只要做了本地提交就可以，`git push origin master`






