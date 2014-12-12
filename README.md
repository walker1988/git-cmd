git命令的基本用法
===============
###1、从远程库克隆项目(*git clone*)
<pre>
$ git clone git@github.com:walker1988/test.git
Cloning into 'test'...
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (3/3), done.
Checking connectivity... done.
</pre>

###2、查看本地库的状态(*git status*)
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

###3、将文件添加到仓库(*git add filename*)
<pre>
$ git add README.md 
</pre>

###4、再次查看本地库状态(*git status*)
<pre>
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   README.md
</pre>

###5、将文件提交到本地仓库(*git commit -m ""*)
<pre>
$ git commit -m "修改READ.md文件"
[master 3f57873] 修改READ.md文件
 1 file changed, 33 insertions(+), 4 deletions(-)
 rewrite README.md (78%)
</pre>


###6、将修改推送到远程仓库(*git push*)
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

