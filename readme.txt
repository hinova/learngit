

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