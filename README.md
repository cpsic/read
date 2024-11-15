GitHub使用文档


1.注册登录账号
1.1 注册
注册地址：https://github.com/ 为国外地址，
连接不稳定，可以使用镜像地址访问：https://kkgithub.com/

进入后按照提示一步步完成即可：

注册成功后点击Sign In 登入

1.2 登录 
进入后如下图，左边是代码仓库和账户信息
也可以使用镜像地址登录 （除注册外都可以使用镜像地址访问）图片显示偶尔有问题不显示，不影响功能

点击进去仓库是代码目录和源码
当前页面可以看到所有的提交记录，切换查看分支，分支的操作


2.软件安装
2.1 本地软件安装
GitHub 命令行工具下载：https://git-scm.com/downloads
选择对应系统的git命令行工具下载后安装
安装完成后鼠标右键会有对应的git命令菜单，使用第二个Bash

git config --global user.name "Your Name" 
git config --global user.email "email@example.com"
也可以不在命令工具中设置，可以在下面vs中设置你的用户名和邮箱

2.2 编译器vs插件
Git安装完成后，重启vs，在选项中选择源代码管理工具；Git


3.Git创建仓库
在Git页面找到仓库，点击进入页面tab（Repositories）,点击右上角的New,输入对应的信息，注意：1.仓库的名称和本地代码项目名称保持一致 2.选择Private，然后配置对应人员


4.代码管理
4.1Git流程
Git 的工作流程主要包括以下几个步骤：初始化仓库、添加文件、提交更改、创建分支、合并分支、解决合并冲突等

4.2代码初始化
如果多人协作，共同修改一个项目的代码，需先将git上代码下载到本地，首次拉取代码通常是通过克隆远程仓库到本地机器来完成的，有多种方式初始化代码到本地文件夹，以下列举常用的三种方式：
4.2.1 选择Open With Visual Studio, 会调用vs直克隆，需要选择你自己的文件夹


4.2.2 直接在代码仓库液面，右边有个Code绿色按钮，点击按钮出现下拉页面，可以直接下载打包好的项目压缩包，解压到本地后双击项目解决方案即可打开

4.2.3 在一个新建好的文件夹内使用git命令工具，点击右键，选择，在弹出的窗口输入命令：git clone + https地址，例如上图中的：https://github.com/yangrui0620/Test.git 
完整命令：git clone https://github.com/yangrui0620/Test.git


4.3Git功能
Git插件在vs上功能比较完善，基本可以不使用命令，直接选择功能进行操作
Vs对应的git管理界面可以对分支进行管理，代码对比，版本还原，解决代码冲突等问题
也可以参考git的操作文档https://git-scm.com/book/en/v2

代码合并的时候可以在网页端看到提交合并的内容，修改的内容，提交的信息，也方便查找问题代码


查看提交的内容，会对改动的代码进行比较，左右两边区分并且高亮显示


5.常见问题
5.3.1 常用命令
git init 
初始化，初始化（创建）本地仓库，可以看到项目文件夹下生成的.git隐藏文件夹。这个文件夹会记录以后每次的更改和提交。
git config --global user.name “name”
初次使用配置个人用户名，如果以前已经配置，通过git config user.name查看
git config --global user.email “email”
初次使用时要先配置个人邮箱，如果以前已经配置，通过git config user.email查看
git remote add origin “git远程仓库地址”
使用链接新增远程仓库origin，如果链接写错了，使用git remote set-url origin “git远程仓库地址”修改链接
git clone 克隆仓库
git add 添加到暂存区
git commit 将暂存区的变更提交
git checkout 切换分支
git branch 创建分支
git push 推送代码
git pull 拉取代码
git remote -v 查看当前配置的远程分支
git config --list 查看当前配置的信息

5.3.2  Git冲突的产生原因
多人同时使用或者操作git中的同一个文件，最后在依次提交commit和推送push的时候，第一个操作的是可以正常提交的，而之后的开发者想要执行pull（拉）和pull（推）操作的时候，就会报冲突异常conflict。
5.3.1  Git解决冲突的方法
a、使用git fetch origin master将远程分支拉下来
b、使用git merge origin master手动合并冲突的内容，首先合并代码并输入备注信息，然后按esc，再按shit+;，输入wq保存并退出
c、使用git add xxx和git commit -m "xxx" 将改动提交
d、使用git push origin master将改动提交到远程分支

