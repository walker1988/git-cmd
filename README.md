git命令的基本用法
===============
>工作区：本地库目录

>版本库：本地库目录中的.git目录

>暂存区

>master分支

>HEAD：指向master分支的指针

###1、配置全局用户名和邮箱
<pre>
$ git config --global user.name "walker"
$ git config --global user.email "walker@163.com"
</pre>

###2、从远程库克隆项目(*git clone*)
<pre>
$ git clone git@github.com:walker1988/test.git
Cloning into 'test'...
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (3/3), done.
Checking connectivity... done.
</pre>

###3、查看本地工作区的状态(*git status*)
<pre>
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
</pre>

###4、将文件修改添加到暂存区(*git add filename*)
<pre>
$ git add README.md 
</pre>

###5、再次查看本地工作区的状态(*git status*)
<pre>
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   README.md
</pre>

###6、将暂存区的文件修改提交到master分支(*git commit -m "remark"*)
<pre>
$ git commit -m "修改READ.md文件"
[master 3f57873] 修改READ.md文件
 1 file changed, 33 insertions(+), 4 deletions(-)
 rewrite README.md (78%)
</pre>

###7、查看版本库中最新版本与工作区指定文件的区别(*git diff HEAD -- fileName*)
<pre>

</pre>

###8、将master分支的修改推送到远程仓库(*git push*)
<pre>
$ git push
Counting objects: 5, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 772 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To git@github.com:walker1988/test.git
   15dffab..3f57873  master -> master
</pre>

