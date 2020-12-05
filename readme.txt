Git is a version control system.
Git is free software.

1.初始化一个Git仓库，使用git init命令。

2.添加文件到Git仓库，分两步：

	1)使用命令git add <file>，注意，可反复多次使用，添加多个文件；
	2)使用命令git commit -m <message>，完成。

3.git status命令可以让我们时刻掌握仓库当前的状态，上面的命令输出告诉我们，readme.txt被修改过了，但还没有准备提交的修改。

4.git diff顾名思义就是查看difference，显示的格式正是Unix通用的diff格式，可以从上面的命令输出看到，我们在第一行添加了一个distributed单词。

5.HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard <commit_id>(其中<commit_id>可以使具体的版本号(简写为前几位)；也可以用HEAD^表示上个版本；HEAD^^表示上上个版本；HEAD~100表示往上100个版本)

6.版本回退
	1）穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。2）要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。(reflog会记录每一次命令)

7.用git status查看一下状态，如果是从来没有被添加过的文件，状态是Untracked files；已经添加过被修改的文件，状态是Changes not staged for commit

8.git add命令实际上就是把要提交的所有修改放到暂存区（Stage），然后，执行git commit就可以一次性把暂存区的所有修改提交到分支

9.进行如下操作：第一次修改 -> git add -> 第二次修改 -> git commit，我们用git status查看当前状态会发现第二次修改并未放到暂存区，当你用git add命令后，在工作区的第一次修改被放入暂存区，准备提交，但是，在工作区的第二次修改并没有放入暂存区，所以，git commit只负责把暂存区的修改提交了，也就是第一次的修改被提交了，第二次的修改不会被提交。（用git diff HEAD -- readme.txt命令可以查看工作区和版本库里面最新版本的区别）
进行这样的操作：第一次修改 -> git add -> 第二次修改 -> git add -> git commit可以正常提交两次的修改。总而言之：每次修改，如果不用git add到暂存区，那就不会加入到commit中。

10.撤销修改
场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。

场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

11.文件删除
git rm test.txt


