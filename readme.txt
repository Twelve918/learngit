Git is a version control system.
Git is free software.

1.初始化一个Git仓库，使用git init命令。

2.添加文件到Git仓库，分两步：

	1)使用命令git add <file>，注意，可反复多次使用，添加多个文件；
	2)使用命令git commit -m <备注>，完成。
3.git status命令可以让我们时刻掌握仓库当前的状态，上面的命令输出告诉我们，readme.txt被修改过了，但还没有准备提交的修改。
4.git diff顾名思义就是查看difference，显示的格式正是Unix通用的diff格式，可以从上面的命令输出看到，我们在第一行添加了一个distributed单词。
5.
