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