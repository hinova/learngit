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
#HEAD ��ǰ�汾
#HEAD^��һ���汾,HEAD^^�������汾��HEAD~100��100���汾

git reset --hard d79d38

git reflog 
#��¼ÿһ������

 git diff HEAD -- readme.txt 
#�Ƚϲֿ����°汾�뱾�ع������汾 


git checkout -- readme.txt
#һ����readme.txt���޸ĺ�û�б��ŵ��ݴ��������ڣ������޸ľͻص��Ͱ汾��һģһ����״̬��

#һ����readme.txt�Ѿ���ӵ��ݴ������������޸ģ����ڣ������޸ľͻص���ӵ��ݴ������״̬��

#��֮������������ļ��ص����һ��git commit��git addʱ��״̬��
#git checkout -- file�����еġ�--������Ҫ��û�С�--�����ͱ���ˡ�����һ���·�֧��������

#����1����������˹�����ĳ���ļ������ݣ���ֱ�Ӷ������������޸�ʱ��������git checkout -- file��

#����2�����㲻�������˹�����ĳ���ļ������ݣ�����ӵ����ݴ���ʱ���붪���޸ģ�����������һ��������git reset HEAD file���ͻص��˳���1���ڶ���������1������


ɾ���ļ�
git add test.txt
git commit -m "add test.txt"

rm test.txt

�ָ���
git checkout -- test.txt

ɾ��
git rm test.txt
git commit -m "remove "

#��ӣ���������SSH Key
ssh-keygen -t rsa -C "your\_email@example.com"

git remote add origin git@github.com:michaelliao/learngit.git

git push -u origin master

$ git push origin master

Ҫ����һ��Զ�̿⣬ʹ������git remote add origin git@server-name:path/repo-name.git��

������ʹ������git push -u origin master��һ������master��֧���������ݣ�

�˺�ÿ�α����ύ��ֻҪ�б�Ҫ���Ϳ���ʹ������git push origin master���������޸ģ�

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


����dev��֧��Ȼ���л���dev��֧
$ git checkout -b dev
Switched to a new branch 'dev'

git checkout�������-b������ʾ�������л����൱�������������
$ git branch dev
$ git checkout dev
Switched to branch 'dev'

��git branch����鿴��ǰ��֧
$ git branch
* dev
  master
  
dev��֧�Ĺ�����ɣ����ǾͿ����л���master��֧
$ git checkout master
Switched to branch 'master'


���ǰ�dev��֧�Ĺ����ɹ��ϲ���master��֧��
PS F:\gitwork\learngit> git merge dev
Updating 59e0b79..3709b9e
Fast-forward
 readme.txt | 17 ++++++++++++++++-
 1 file changed, 16 insertions(+), 1 deletion(-)
PS F:\gitwork\learngit> git branch
  dev
* master

�ϲ���ɺ󣬾Ϳ��Է��ĵ�ɾ��dev��֧��
$ git branch -d dev
Deleted branch dev (was fec145a).

$ git branch
* master

Git��������ʹ�÷�֧��

�鿴��֧��git branch

������֧��git branch name

�л���֧��git checkout name

����+�л���֧��git checkout -b name

�ϲ�ĳ��֧����ǰ��֧��git merge name

ɾ����֧��git branch -d name

�ô�������git logҲ���Կ�����֧�ĺϲ������
$ git log --graph --pretty=oneline --abbrev-commit
*   59bc1cb conflict fixed
|\
| * 75a857c AND simple
* | 400b400 & simple
|/
* fec145a branch test
...


Git���á�Fast forward��ģʽ��������ģʽ�£�ɾ����֧�󣬻ᶪ����֧��Ϣ
DEV...
׼���ϲ�dev��֧����ע��--no-ff��������ʾ���á�Fast forward����
git merge --no-ff -m "merge with no-ff" dev
git log --graph --pretty=oneline --abbrev-commit

��֧����
��ʵ�ʿ����У�����Ӧ�ð��ռ�������ԭ����з�֧����

���ȣ�master��֧Ӧ���Ƿǳ��ȶ��ģ�Ҳ���ǽ����������°汾��ƽʱ����������ɻ

�����ĸɻ��أ��ɻ��dev��֧�ϣ�Ҳ����˵��dev��֧�ǲ��ȶ��ģ���ĳ��ʱ�򣬱���1.0�汾����ʱ���ٰ�dev��֧�ϲ���master�ϣ���master��֧����1.0�汾��

������С�����ÿ���˶���dev��֧�ϸɻÿ���˶����Լ��ķ�֧��ʱ��ʱ����dev��֧�Ϻϲ��Ϳ����ˡ�

���ԣ��ŶӺ����ķ�֧����������������


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
* 956067a �ϲ���֧
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


��֧����
��ʵ�ʿ����У�����Ӧ�ð��ռ�������ԭ����з�֧����

���ȣ�master��֧Ӧ���Ƿǳ��ȶ��ģ�Ҳ���ǽ����������°汾��ƽʱ����������ɻ

�����ĸɻ��أ��ɻ��dev��֧�ϣ�Ҳ����˵��dev��֧�ǲ��ȶ��ģ���ĳ��ʱ�򣬱���1.0�汾����ʱ���ٰ�dev��֧�ϲ���master�ϣ���master��֧����1.0�汾��

������С�����ÿ���˶���dev��֧�ϸɻÿ���˶����Լ��ķ�֧��ʱ��ʱ����dev��֧�Ϻϲ��Ϳ����ˡ�

���ԣ��ŶӺ����ķ�֧����������������

С��
Git��֧ʮ��ǿ�����Ŷӿ�����Ӧ�ó��Ӧ�á�

�ϲ���֧ʱ������--no-ff�����Ϳ�������ͨģʽ�ϲ����ϲ������ʷ�з�֧���ܿ��������������ϲ�����fast forward�ϲ��Ϳ����������������ϲ���



Bug��֧
��������У�bug����ҳ��㷹һ��������bug����Ҫ�޸�����Git�У����ڷ�֧����˵�ǿ�����ԣ�ÿ��bug������ͨ��һ���µ���ʱ��֧���޸����޸��󣬺ϲ���֧��Ȼ����ʱ��֧ɾ����

����ӵ�һ���޸�һ������101��bug������ʱ������Ȼ�أ����봴��һ����֧issue -101���޸��������ǣ��ȵȣ���ǰ����dev�Ͻ��еĹ�����û���ύ��


fix bug

�������㲻���ύ�����ǹ���ֻ���е�һ�룬��û���ύ��Ԥ����ɻ���1��ʱ�䡣���ǣ�����������Сʱ���޸���bug����ô�죿

�Һã�Git���ṩ��һ��stash���ܣ����԰ѵ�ǰ�����ֳ������ء����������Ժ�ָ��ֳ������������

$ git stash
Saved working directory and index state WIP on dev: 6224937 add merge
HEAD is now at 6224937 add merge

$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 6 commits.
$ git checkout -b issue-101
Switched to a new branch 'issue-101'

$ git add readme.txt 
$ git commit -m "fix bug 101"
[issue-101 cc17032] fix bug 101
 1 file changed, 1 insertion(+), 1 deletion(-)
 
 $ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 2 commits.
$ git merge --no-ff -m "merged bug fix 101" issue-101
Merge made by the 'recursive' strategy.
 readme.txt |    2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
$ git branch -d issue-101
Deleted branch issue-101 (was cc17032).

$ git checkout dev
Switched to branch 'dev'
$ git status
# On branch dev
nothing to commit (working directory clean)

$ git stash list
stash@{0}: WIP on dev: 6224937 add merge

�����ֳ����ڣ�Git��stash���ݴ���ĳ���ط��ˣ�������Ҫ�ָ�һ�£��������취��

һ����git stash apply�ָ������ǻָ���stash���ݲ���ɾ��������Ҫ��git stash drop��ɾ����

��һ�ַ�ʽ����git stash pop���ָ���ͬʱ��stash����Ҳɾ�ˣ�

$ git stash pop
# On branch dev
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#       new file:   hello.py
#
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#       modified:   readme.txt
#
Dropped refs/stash@{0} (f624f8e5f082f2df2bed8a4e09c12fd2943bdd40)

С��
�޸�bugʱ�����ǻ�ͨ�������µ�bug��֧�����޸���Ȼ��ϲ������ɾ����

����ͷ����û�����ʱ���Ȱѹ����ֳ�git stashһ�£�Ȼ��ȥ�޸�bug���޸�����git stash pop���ص������ֳ���

Feature��֧
$ git checkout -b feature-vulcan
Switched to a new branch 'feature-vulcan'

�л�dev��׼���ϲ���

$ git checkout dev

���ڴ�ʱ���ӵ��ϼ�����򾭷Ѳ��㣬�¹��ܱ���ȡ����

��Ȼ�׸��ˣ����������֧���Ǳ���͵����٣�

$ git branch -d feature-vulcan
error: The branch 'feature-vulcan' is not fully merged.
If you are sure you want to delete it, run 'git branch -D feature-vulcan'.
����ʧ�ܡ�Git�������ѣ�feature-vulcan��֧��û�б��ϲ������ɾ��������ʧ���޸ģ����Ҫǿ��ɾ������Ҫʹ������git branch -D feature-vulcan��

��������ǿ��ɾ����

$ git branch -D feature-vulcan
Deleted branch feature-vulcan (was 756d4af).

С��
����һ����feature������½�һ����֧��

���Ҫ����һ��û�б��ϲ����ķ�֧������ͨ��git branch -D nameǿ��ɾ��