http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/0013758410364457b9e3d821f4244beb0fd69c61a185ae0000

git config --global user.name "hinova"
git config --global user.email "novakr@126.com"

git init

git add readme.txt
git commit -m "xxxx"

git status
git diff readme.txt

git log

git reset --hard HEAD^ 
#HEAD 当前版本
#HEAD^上一个版本,HEAD^^上两个版本，HEAD~100上100个版本

git reset --hard d79d38

git reflog 
#记录每一次命令

 git diff HEAD -- readme.txt 
#比较仓库最新版本与本地工作区版本 


git checkout -- readme.txt
#一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；

#一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

#总之，就是让这个文件回到最近一次git commit或git add时的状态。
#git checkout -- file命令中的“--”很重要，没有“--”，就变成了“创建一个新分支”的命令

#场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

#场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。


删除文件
git add test.txt
git commit -m "add test.txt"

rm test.txt

恢复：
git checkout -- test.txt

删除
git rm test.txt
git commit -m "remove "

#添加，创建创建SSH Key
ssh-keygen -t rsa -C "your\_email@example.com"

git remote add origin git@github.com:michaelliao/learngit.git

git push -u origin master

$ git push origin master

要关联一个远程库，使用命令git remote add origin git@server-name:path/repo-name.git；

关联后，使用命令git push -u origin master第一次推送master分支的所有内容；

此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；

Create a new repository on the command line

touch README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/hinova/java.git
git push -u origin master
Push an existing repository from the command line

git remote add origin https://github.com/hinova/java.git
git push -u origin master


创建dev分支，然后切换到dev分支
$ git checkout -b dev
Switched to a new branch 'dev'

git checkout命令加上-b参数表示创建并切换，相当于以下两条命令：
$ git branch dev
$ git checkout dev
Switched to branch 'dev'

用git branch命令查看当前分支
$ git branch
* dev
  master
  
dev分支的工作完成，我们就可以切换回master分支
$ git checkout master
Switched to branch 'master'


我们把dev分支的工作成果合并到master分支上
PS F:\gitwork\learngit> git merge dev
Updating 59e0b79..3709b9e
Fast-forward
 readme.txt | 17 ++++++++++++++++-
 1 file changed, 16 insertions(+), 1 deletion(-)
PS F:\gitwork\learngit> git branch
  dev
* master

合并完成后，就可以放心地删除dev分支了
$ git branch -d dev
Deleted branch dev (was fec145a).

$ git branch
* master

Git鼓励大量使用分支：

查看分支：git branch

创建分支：git branch name

切换分支：git checkout name

创建+切换分支：git checkout -b name

合并某分支到当前分支：git merge name

删除分支：git branch -d name

用带参数的git log也可以看到分支的合并情况：
$ git log --graph --pretty=oneline --abbrev-commit
*   59bc1cb conflict fixed
|\
| * 75a857c AND simple
* | 400b400 & simple
|/
* fec145a branch test
...


Git会用“Fast forward”模式，但这种模式下，删除分支后，会丢掉分支信息
DEV...
准备合并dev分支，请注意--no-ff参数，表示禁用“Fast forward”：
git merge --no-ff -m "merge with no-ff" dev
git log --graph --pretty=oneline --abbrev-commit

分支策略
在实际开发中，我们应该按照几个基本原则进行分支管理：

首先，master分支应该是非常稳定的，也就是仅用来发布新版本，平时不能在上面干活；

那在哪干活呢？干活都在dev分支上，也就是说，dev分支是不稳定的，到某个时候，比如1.0版本发布时，再把dev分支合并到master上，在master分支发布1.0版本；

你和你的小伙伴们每个人都在dev分支上干活，每个人都有自己的分支，时不时地往dev分支上合并就可以了。

所以，团队合作的分支看起来就像这样：


PS F:\gitwork\learngit> git merge --no-ff -m "merge with no-ff" dev
Merge made by the 'recursive' strategy.
 readme.txt | 2 ++
 1 file changed, 2 insertions(+)
PS F:\gitwork\learngit> git branch
  dev
* master
PS F:\gitwork\learngit> git log --graph --pretty=oneline --abbrev-commit
*   5967648 merge with no-ff
|\
| * e9c462c add dev text
|/
* 9133b00 xxxxxxxxxx
* 956067a 合并分支
*   2bb3748 conflict fixed
|\
| * cc1c52c branch
| * 1532588 branch
* | 8dc0b56 master
|/
* dfb4c3e merge dev
* 3709b9e add branch
* 59e0b79  add
* 0861bbd add git push
* 5df5bac add readme.txt