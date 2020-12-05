Git is a version control system.
Git is free software.

1.初始化一个Git仓库，使用git init命令。

2.添加文件到Git仓库，分两步：

	1)使用命令git add <file>，注意，可反复多次使用，添加多个文件；
	2)使用命令git commit -m <message>，完成。

3.git status命令可以让我们时刻掌握仓库当前的状态，上面的命令输出告诉我们，readme.txt被修改过了，但还没有准备提交的修改。

4.git diff顾名思义就是查看difference，显示的格式正是Unix通用的diff格式，可以从上面的命令输出看到，我们在第一行添加了一个distributed单词。

5.HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard <commit_id>(其中<commit_id>可以使具体的版本号(简写为前几位)；也可以用HEAD^表示上个版本；HEAD^^表示上上个版本；HEAD~100表示往上100个版本)

6.
	1）穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。2）要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。(reflog会记录每一次命令)

7.用git status查看一下状态，如果是从来没有被添加过的文件，状态是Untracked files；已经添加过被修改的文件，状态是Changes not staged for commit

8.git add命令实际上就是把要提交的所有修改放到暂存区（Stage），然后，执行git commit就可以一次性把暂存区的所有修改提交到分支

9.test
